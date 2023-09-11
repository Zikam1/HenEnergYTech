<template>
  <div>
    <header>
      <nav
        class="container mx-auto p-4 py-5 flex justify-between items-center text-sm"
      >
        <NuxtLink to="/">
          <img src="/logo.png" class="h-[25px]" />
        </NuxtLink>

        <button
          @click="toggleNav"
          class="block md:hidden text-black focus:outline-none"
        >
          <svg
            class="h-6 w-6 fill-current"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 24 24"
          >
            <path
              fill-rule="evenodd"
              d="M3.75 5h16.5a.75.75 0 110 1.5H3.75a.75.75 0 110-1.5zm0 5h16.5a.75.75 0 110 1.5H3.75a.75.75 0 110-1.5zm0 5h16.5a.75.75 0 110 1.5H3.75a.75.75 0 110-1.5z"
            ></path>
          </svg>
        </button>

        <ul
          v-if="navOpen === true"
          class="cursor-pointer absolute right-20 top-12 bg-white z-10 p-5 border shadow-md"
        >
          <span @click="navOpen = false">close</span>
          <div
            class="px-4 py-2 hover:bg-gray-200"
            v-for="link in navLinks"
            :key="link"
          >
            <NuxtLink :to="link.route">
              {{ link.link }}
            </NuxtLink>
          </div>
        </ul>

        <ul
          v-else
          :class="['hidden', navOpen ? 'block' : '']"
          class="md:flex sm:gap-5"
        >
          <div v-for="link in navLinks" :key="link">
            <NuxtLink :to="link.route">
              {{ link.link }}
            </NuxtLink>
          </div>
        </ul>
      </nav>
    </header>

    <!-- Output page content -->
    <div class="container mx-auto px-4 text-sm">
      <slot />
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const navOpen = ref(false);
const navLinks = ref([
  {
    link: "Products",
    route: "/products",
  },
  {
    link: "Services",
    route: "/services",
  },
  {
    link: "News & Events",
    route: "/about",
  },
  {
    link: "Company",
    route: "/contact-us",
  },
]);

const toggleNav = () => {
  navOpen.value = !navOpen.value;
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Albert+Sans:wght@300;400;500;600;700&display=swap");
</style>
