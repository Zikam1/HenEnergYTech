<template>
  <article>
    <div class="relative">
      <img :src="service.image" alt="" class="h-[200px] object-cover w-full" />
      <div class="absolute inset-0 bg-[rgba(0,0,0,0.5)]" />
    </div>

    <div>
      <h2 class="mt-7 font-semibold text-2xl">{{ service.title }}</h2>
      <p class="mt-3 description overflow-hidden text-ellipsis">
        {{ service.description }}
      </p>
      <NuxtLink
        v-if="show"
        :to="service.link"
        class="mt-4 block bg-[#092A6D] px-4 py-2 w-max text-white rounded-md"
      >
        Learn more
      </NuxtLink>
    </div>
  </article>
</template>

<script setup>
const { service, show } = defineProps(["service", "show"]);
</script>

<style scoped>
.description {
  -webkit-line-clamp: 4;
  -webkit-box-orient: vertical;
  display: -webkit-box;
}
</style>
