<template>
  <div class="mb-4">
    <label class="block text-gray-700 text-sm font-bold mb-2" :for="id">{{ label }}</label>
    <input @input="$emit('input', $event.target.value)" :value="value" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline" :id="id" :type="type" :placeholder="placeholder" required />
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
      default: 'text'
    },
    id: {
      type: String,
      default: 'field__' + Math.floor(Math.random() * 100)
    },
    placeholder: {
      type: String,
      default: 'Please fill in this field.'
    }
  }
}
</script>

<style>

</style>
