<template>
  <form class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4">

    <form-field class="mb-4" v-model="name" label="Name" placeholder="Your Name" />
    <form-field class="mb-4" v-model="company" label="Company" placeholder="Company Name" />
    <form-field class="mb-4" v-model="occupation" label="Occupation" placeholder="Your Occupation" />
    <form-field class="mb-4" v-model="email" label="Email" type="email" placeholder="Your Best Email" />
    <form-field class="mb-4" v-model="phone" label="Phone" type="tel" placeholder="Your Best Phone Number" />
    <form-field class="mb-4" v-model="avatarImg" label="Avatar Image" type="text" placeholder="Your Avatar Image URL" />

    <div class="flex items-center justify-between">
      <a class="inline-block align-baseline font-bold text-sm text-red-500 hover:text-red-800" href="#">
        Clear All
      </a>
      <button @click="submitUser" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline" type="button">
        Submit
      </button>
    </div>
  </form>
</template>

<script>
import FormField from './FormField'

export default {
  components: {
    FormField
  },
  data () {
    return {
      name: '',
      occupation: '',
      company:  '',
      email: '',
      phone: null,
      avatarImg: ''
    }
  },
  methods: {
    submitUser () {
      this.$emit('submitUser', {
        name: this.name,
        occupation: this.occupation,
        company: this.company,
        email: this.email,
        phone: this.phone,
        avatarImg: this.avatarImg
      })
    }
  }
};
</script>
