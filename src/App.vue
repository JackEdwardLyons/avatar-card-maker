<template>
  <section class="font-sans" v-cloak>
    <responsive-header @changeProfileCardLayout="(payload) => selectedLayout = payload" />
    <main class="bg-gray-400">
      <div class="flex flex-col-reverse pt-32 md:pt-16 md:flex-row items-center justify-center bg-gray-400 ">
        <div class="w-full max-w-lg md:w-1/2 p-4 ">
          <input-card @submitUser="submitUser" />
        </div>
        <section class="w-full max-w-md sm:w-1/2 pb-16 py-auto">
          <profile-card
            v-if="selectedLayout === 'vertical'"
            :name="name"
            :occupation="occupation"
            :company="company"
            :email="email"
            :phone="phone"
            :avatarImg="avatarImg"
          />
          <slim-profile-card
            v-else
            :name="name"
            :occupation="occupation"
            :company="company"
            :email="email"
            :phone="phone"
            :avatarImg="avatarImg"
          />
        </section>
      </div>
    </main>
  </section>
</template>

<script>
import InputCard from './components/InputCard'
import ProfileCard from './components/ProfileCard'
import SlimProfileCard from './components/SlimProfileCard'
import ResponsiveHeader from './components/ResponsiveHeader'

export default {
  name: 'app',
  components: {
    ProfileCard,
    InputCard,
    SlimProfileCard,
    ResponsiveHeader
  },
  data() {
    return {
      name: '',
      occupation: '',
      company: '',
      email: '',
      phone: '',
      avatarImg: undefined,
      selectedLayout: 'vertical'
    }
  },
  methods: {
    submitUser ({ name, occupation, company, email, phone, avatarImg }) {
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

