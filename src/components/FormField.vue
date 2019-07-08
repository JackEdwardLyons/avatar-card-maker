<template>
  <div class="mb-4">
    <div v-if="type !== 'file'">
      <label class="block text-gray-700 text-sm font-bold mb-2" :for="id">{{ label }}</label>
      <input
        @input="$emit('input', $event.target.value)"
        :value="value"
        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
        :id="id"
        :type="type"
        :placeholder="placeholder"
        required
      />
    </div>

    <div v-else>
      <label class="block text-gray-700 text-sm font-bold mb-2" for="upload-input">Avatar Image</label>
      <div class="flex" :class="{ 'justify-around': uploadFile.image }">
        <input 
          id="upload-input" 
          type="file" 
          @change.prevent="onFileChange" 
          accept="image/*" 
        />
        <img
          v-show="uploadFile.image"
          class="rounded-full w-12 h-12 shadow-md upload-img"
          :src="uploadFile.image"
          alt="Your uploaded avatar image"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    value: {
      type: String
    },
    label: {
      type: String,
      required: true
    },
    type: {
      type: String,
      default: "text"
    },
    id: {
      type: String,
      default: "field__" + Math.floor(Math.random() * 100)
    },
    placeholder: {
      type: String,
      default: "Please fill in this field."
    }
  },
  data() {
    return {
      uploadFile: {
        name: '',
        image: ''
      }
    }
  },
  methods: {
    onFileChange (e) {
      let files = e.target.files || e.dataTransfer.files
      if (!files.length) return
      return this.createImage(files[0])
    },
    createImage: function(file) {
      let reader = new FileReader()
      this.uploadFile.name = file.name

      reader.onload = e => {
        this.uploadFile.image = e.target.result
        this.$emit('input', this.uploadFile.image)
      }

      return reader.readAsDataURL(file)
    }
  }
}
</script>

