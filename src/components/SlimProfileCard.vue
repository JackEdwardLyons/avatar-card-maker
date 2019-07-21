<template>
  <article class="flex h-20 bg-white justify-between shadow-lg mx-auto max-w-md rounded">
    <div class="flex">
      <div class="flex-shrink-0 w-20">
        <img class="w-auto md:h-full" :src="avatarImg" alt="Woman paying for a purchase">
      </div>
      <div class="flex items-center justify-center mx-2" v-if="!name || !occupation || !company">
        <p class="text-sm leading-tight text-gray-900">Please enter your name, occupation and company details.</p>
      </div>
      <div class="mx-2" v-else>
        <p class="block mt-1 text-lg font-semibold text-gray-900">{{ name }}</p>
        <div class="uppercase tracking-wide text-sm text-gray-600">{{ occupation }}</div>
        <div class="uppercase tracking-wide text-sm text-blue-800 font-bold">{{ company }}</div>
      </div>
    </div>
    <div class="flex flex-col">
      <a 
        :href="`tel:${phone}`" 
        class="flex items-center justify-center flex-1 bg-green-500 hover:bg-green-700 text-white font-bold px-4 focus:outline-none focus:shadow-outline"
        v-text="'Call'"
      />
      <a 
        :href="`mailto:${email}`" 
        class="flex items-center justify-center flex-1 bg-blue-500 hover:bg-blue-700 text-white font-bold px-4 focus:outline-none focus:shadow-outline"
        v-text="'Message'"
      />
    </div>
  </article>
</template>

<script>
export default {
  name: "ProfileCard",
  props: {
    name: {
      type: String,
    },
    occupation: {
      type: String,
    },
    company: {
      type: String,
    },
    email: {
      type: String,
    },
    phone: {
      type: [String, Number],
    },
    avatarImg: {
      type: String,
      default: 'https://www.w3schools.com/howto/img_avatar2.png'
    }
  },
  computed: {
    customFontSizeBasedOnTextLength () {
      return (vueProp) => {
        const nameLength = this[vueProp].length
        return {
          'text-lg': nameLength < 16,
          'text-md': nameLength > 16 && nameLength < 18,
          'text-sm': nameLength >= 18 && nameLength < 21,
          'text-xs': nameLength >= 21
        }
      }
    }
  }
}
</script>
