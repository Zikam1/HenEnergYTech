<template>
    <section
        class="hero relative h-[31rem] lg:h-[36rem] flex items-center text-white"
    >
        <div class="px-4 sm:px-10 md:px-20">
            <h1 class="text-[2.5rem] leading-[2.5rem] font-semibold">
                Co-creating digitalisation solutions
            </h1>
            <p class="mt-[2rem] w-[90%] md:w-[60%] text-base">
                Our mission is to co-create innovative technology solutions for
                enterprises to accelerate adoption of sustainable digitalisation
                practices.
            </p>
            <button class="explore-btn">Explore</button>
        </div>
    </section>

    <section class="mt-14">
        <!-- border-l-4 md:border-l-8 pl-3 border-[#b92227] -->
        <h2
            class="text-2xl sm:text-4xl font-bold mb-8 border-l-4 md:border-l-8 pl-3 border-[#b92227]"
        >
            Services
        </h2>
        <div
            class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-y-10 gap-x-6 mb-8"
        >
            <ServiceCard
                v-for="service in SERVICES"
                :key="service.title"
                :service="service"
            />
        </div>
    </section>
</template>

<script setup>
const SERVICES = [
    {
        title: "WRM Digitalisation",
        description:
            "Our professionals have a thorough understanding of the fundamental physical and mathematical concepts that control many engineering challenges, we apply many of these principles in the development of specialized business intelligent software to address some of these issues for energy providers.",
        link: "/wrm-digitalisation",
        image: "/images/hero.webp",
    },
    {
        title: "Integrated Asset Mangement",
        description:
            "Our IAM services leverage latest technology and digital oilfield solutions to improve traditional asset management processes across the value chain (reservoir to sales point) in order to reduce cost, increase production, improve HSE and optimise processes",
        link: "/integrated-asset-management",
        image: "/images/hero.webp",
    },
    {
        title: "E & P Enterprise Planning",
        description:
            "Our professionals have a thorough understanding of the fundamental physical and mathematical concepts that control many engineering challenges, we apply many of these principles in the development of specialized business intelligent software to address some of these issues for energy providers.",
        link: "/ep-enterprise-planning",
        image: "/images/hero.webp",
    },
    {
        title: "Low & Zero Carbon",
        description:
            "We are committed to working with industries, institutions, and government to identify and deploy cost-effective strategies and digital solutions to achieving net-zero emission operations",
        link: "/low-and-zero-carbon",
        image: "/images/hero.webp",
    },
];
</script>

<style scoped>
.hero {
    background: linear-gradient(
            90deg,
            rgba(0, 0, 0, 0.8),
            rgba(0, 0, 0, 0.6),
            rgba(0, 0, 0, 0.7)
        ),
        url("/images/hero.webp") no-repeat 50% 50% / cover;
}
.explore-btn {
    border: 0;
    background-image: linear-gradient(to bottom, var(--tw-gradient-stops));
    --tw-gradient-from: #b92227;
    --tw-gradient-stops: var(--tw-gradient-from),
        var(--tw-gradient-to, rgba(185, 34, 39, 0));
    --tw-gradient-to: #8e1a1e;
    text-transform: uppercase;
    --tw-text-opacity: 1;
    @apply py-3 px-6 border-b-2 font-medium mt-7 rounded-full;
}
</style>
