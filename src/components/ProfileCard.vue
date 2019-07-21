<template>
  <article class="mx-auto max-w-sm">
    <div class="sm:w-full bg-white rounded-lg shadow-lg leading-tight">
      <div class="border-b px-4 pb-6">
        <div class="text-center flex mb-4">
          <img 
            class="h-32 w-32 rounded-full border-4 border-white -mt-12 mx-auto" 
            :src="avatarImg" 
            alt="Avatar image"
          />
        </div>
        <div class="profile-information" v-if="!name || !occupation || !company">
          <p class="text-center">
            Please enter your name, occupation and company details.
          </p>
        </div>
        <div class="profile-information" v-else>
          <h3 class="font-bold text-2xl mb-1 text-center">
            {{ name }}
          </h3>
          <p class="text-center mt-2 text-lg">
            {{ `${occupation} at ${company}` }}
          </p>
          <p class="text-center my-4">
            <strong>email:</strong> {{ email }}
          </p> 
          <p class="text-center my-4">
            <strong>phone:</strong> {{ phone }}
          </p> 
        </div>
      </div>
      <div class="px-4 py-4">
          <div class="flex justify-center text-grey-darker mb-4">
              <span class="font-semibold">Contact me</span>
          </div>
          <div class="flex">
            <a
              :href="`tel:${phone}`" 
              class="text-center flex-1 rounded-full border-2 bg-blue-500 hover:bg-blue-600 border-grey text-white antialiased font-bold hover:bg-blue-dark px-4 py-2 mr-2"
              v-text="'Phone'"
            />
            <a
              :href="`mailto:${email}`" 
              class="text-center flex-1 rounded-full border-2 hover:bg-gray-200 border-grey font-semibold text-black px-4 py-2" 
              v-text="'Message'"
            />
          </div>
      </div>
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
  }
}
</script>
