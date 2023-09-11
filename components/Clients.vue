<template>
  <div class="pt-4 md:pt-16 2xl:pt-32 mb-12">
    <div class="mx-auto w-3/5 flex flex-col items-center mb-7">
      <h2 class="text-2xl sm:text-3xl font-bold mb-3 capitalize">
        Our Clients
      </h2>
    </div>
  </div>
  <div>
    <div class="">
      <Swiper
        class="swiper"
        :slides-per-view="4"
        :pagination="{ clickable: true, dynamicBullets: true }"
      >
        <SwiperSlide
          v-for="company in companies"
          :key="company.name"
          class="slide"
        >
          <img
            class="company-card-image"
            :src="'/images/' + company.logo"
            :alt="company.name"
          />
          <p class="company-card-title">{{ company.name }}</p>
        </SwiperSlide>
      </Swiper>
    </div>
  </div>
</template>

<script setup lang="ts">
import companies from "../companies.json";
import { Swiper, SwiperSlide } from "Swiper/vue";
//import Swiper from "vue-awesome-swiper";

// import swiper module styles
import "swiper/css";
import "swiper/css/pagination";
// more module style...

const option = ref({});
</script>

<style scoped>
.companies {
  @apply mx-auto w-3/5 flex-1 flex-col items-center grid grid-cols-2;
}
/* .company-card {
  @apply flex flex-col items-center p-8;
  @apply transition-all cursor-pointer;
} */
</style>
