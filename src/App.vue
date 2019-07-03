<template>
  <div id="app" class="font-sans">
    <ResponsiveHeader />
      <!-- Two columns -->
      <div class="bg-gray-400 pt-10 responsive-height">
        <div class="flex flex-col-reverse md:flex-row items-center justify-center">
          <div class="w-full sm:w-1/2 md:w-1/2 p-4 inline">
            <InputCard @submitUser="logItOut" />
          </div>
          <div class="w-full sm:w-1/2 md:w-1/2 p-4 inline">
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
      avatarImg: ''
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
<style scoped>
.responsive-height {
  height: 100%;
}
@media screen and (min-width: 766px) {
  .responsive-height {
    /* height: 100vh; */
  }
}

</style>

