<template>
  <div class="font-sans" v-cloak>
    <ResponsiveHeader />
      <!-- Two columns -->
      <div class="bg-gray-400">
        <div class="flex flex-col-reverse pt-32 md:pt-16 md:flex-row items-center justify-center bg-gray-400 ">
          <div class="w-full max-w-lg md:w-1/2 p-4 ">
            <InputCard @submitUser="logItOut" />
          </div>
          <div class="w-full max-w-md sm:w-1/2 pb-16 py-auto">
            <ProfileCard
              :name="name"
              :occupation="occupation"
              :company="company"
              :email="email"
              :phone="phone"
              :avatarImg="avatarImg"
            />
          </div>
        </div>
      </div>
  </div>
</template>

<script>
import InputCard from './components/InputCard'
import ProfileCard from './components/ProfileCard'
import ResponsiveHeader from './components/ResponsiveHeader'

export default {
  name: 'app',
  components: {
    ProfileCard,
    InputCard,
    ResponsiveHeader
  },
  data() {
    return {
      name: '',
      occupation: '',
      company: '',
      email: '',
      phone: '',
      avatarImg: undefined
    }
  },
  methods: {
    logItOut ({ name, occupation, company, email, phone, avatarImg }) {
      // eslint-disable-next-line
      this.name = name
      this.occupation = occupation
      this.company = company
      this.email = email
      this.phone = phone
      this.avatarImg = avatarImg
    }
  }
}
</script>
<style>
  
</style>
