<template>
  <section class="mx-auto">

      <div class="sm:w-full md:w-1/2 mx-auto bg-white rounded-lg shadow-lg leading-tight">
        <div class="border-b px-4 pb-6">
          <div class="text-center flex mb-4">
            <img 
              class="h-32 w-32 rounded-full border-4 border-white -mt-12 mx-auto" 
              src="https://randomuser.me/api/portraits/women/21.jpg" 
              alt="Avatar image"
            />
          </div>
          <div class="profile-information">
            <h3 class="font-bold text-2xl mb-1 text-center">{{ name }}</h3>
            <p class="text-center">{{ `${occupation} at ${company}` }}</p>
            <p class="text-center my-4"><strong>email:</strong> {{ email }}</p> 
            <p class="text-center my-4"><strong>phone:</strong> {{ phone }}</p> 
          </div>
        </div>
        <div class="px-4 py-4">
            <div class="flex justify-center text-grey-darker mb-4">
                <span class="font-semibold">Contact me</span>
            </div>
            <div class="flex">
              <button class="flex-1 rounded-full border-2 bg-blue-500 hover:bg-blue-600 border-grey text-white antialiased font-bold hover:bg-blue-dark px-4 py-2 mr-2">Phone</button>
              <button class="flex-1 rounded-full border-2 hover:bg-gray-200 border-grey font-semibold text-black px-4 py-2">Message</button>
            </div>
        </div>
      </div>
  </section>
</template>

<script>
export default {
  name: "ProfileCard",
  props: {
    name: {
      type: String,
      default: ''
    },
    occupation: {
      type: String,
      default: ''
    },
    company: {
      type: String,
      default: ''
    },
    email: {
      type: String,
      default: ''
    },
    phone: {
      type: [String, Number],
      default: ''
    },
    avatarImg: {
      type: String,
      default: 'https://www.radiotodaybd.fm/wp-content/uploads/2019/02/img_avatar.png?fbclid=IwAR2LEIMdiKkcJws2jrY7lV3VeatrQf7EhcferhX1NWJ-40W9NUCjbeiiOGY'
    }
  }
};
</script>
