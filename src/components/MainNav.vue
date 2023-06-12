<template>
  <header class="w-full text-sm">
    <div class="fixed top-0 left-0 w-full h-16 bg-white">
      <div class="flex flex-nowrap h-full px-8 mx-auto border-b border-solid border-brand-blue-1">
        <a :href="url" class="flex items-center h-full text-xl">{{ company }}</a>

        <nav class="h-full ml-12">
          <ul class="flex h-full p-0 m-0 list-none">

            <li class="h-full ml-9 first:ml-0" v-for="menuItem in menuItems" :key="menuItem">
              <a href="" class="flex items-center h-full py-2.5">{{ menuItem }}</a>
            </li>

          </ul>
        </nav>


        <div class="flex items-center h-full ml-auto">
          <profile-image v-if="isLoggedIn" />
          <action-button v-else v-on:click="loginUser" />
        </div>

      </div>

    </div>
  </header>
</template>

<script>
import ActionButton from "@/components/ActionButton.vue";
import ProfileImage from '@/components/ProfileImage.vue';


export default {
  name: "Main Nav",
  components: {
    ActionButton,
    ProfileImage,
  },
  data() {
    return {
      company: "Bobo Careers",
      url: "http://careers.google.com",
      menuItems: ["Teams", "Locations", "Life at Bobo Corp", "How we hire", "Students", "Jobs"],
      isLoggedIn: false,
    }
  },
  methods: {
    loginUser() {
      this.isLoggedIn = true;
    }
  }
};
</script>
