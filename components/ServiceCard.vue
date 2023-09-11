<template>
    <article>
        <div class="relative">
            <img :src="service.image" alt="" class="" />
            <div class="absolute inset-0 bg-[rgba(0,0,0,0.5)]" />
        </div>

        <div>
            <h2 class="mt-7 font-semibold text-2xl">{{ service.title }}</h2>
            <p class="mt-3 description overflow-hidden text-ellipsis">
                {{ service.description }}
            </p>
            <NuxtLink :to="service.link" class="mt-4 block">
                <button class="bg-[#092A6D] px-4 py-2 text-white rounded-md">
                    Learn more
                </button>
            </NuxtLink>
        </div>
    </article>
</template>


<script setup>
const { service } = defineProps(["service"]);
</script>

<style scoped>
.description {
    -webkit-line-clamp: 4;
    -webkit-box-orient: vertical;
    display: -webkit-box;
}
</style>