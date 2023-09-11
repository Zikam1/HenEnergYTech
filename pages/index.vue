<template>
  <section
    class="hero relative h-[31rem] lg:h-[36rem] flex items-center text-white"
  >
    <div class="px-4 sm:px-10 md:px-20">
      <h1 class="text-[2.5rem] leading-[2.5rem] font-semibold">
        Developing Digitalization Solutions
      </h1>
      <p class="mt-[2rem] w-[90%] md:w-[60%] text-base">
        Our goal is to partner in crafting pioneering technological answers that
        help businesses swiftly integrate sustainable digital practices..
      </p>
      <button class="explore-btn">Discover</button>
    </div>
  </section>

  <section class="mt-14">
    <!-- border-l-4 md:border-l-8 pl-3 border-[#b92227] -->
    <h2
      class="text-2xl sm:text-4xl font-bold mb-8 border-l-4 md:border-l-8 pl-3 border-[#b92227]"
    >
      Energy Technology Services
    </h2>
    <div
      class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-y-10 gap-x-6 mb-24"
    >
      <ServiceCard
        v-for="service in SERVICES"
        :key="service.title"
        :service="service"
        :show="true"
      />
    </div>
  </section>
  <section
    class="light relative flex flex-col-reverse lg:flex-row lg:flex-wrap gap-5 items-center #092A6D bg-blue-800 text-white"
  >
    <div class="h-[250px] md:h-auto flex-1">
      <img src="../images/light.jpg" class="h-full w-full object-cover" />
    </div>
    <div class="px-4 py-8 md:flex-1">
      <h2 class="text-3xl md:text-4xl font-semibold mb-4">Technology Expert</h2>
      <p class="text-base">
        We are known as high-skilled marketplace and we see an acute pain point
        within that area
      </p>
      <button
        class="bg-white hover:bg-gray-200 text-blue-500 font-semibold mt-6 py-2 px-4 border border-blue-500 rounded"
      >
        Read More
      </button>
    </div>
  </section>

  <!-- <Our solution> -->
  <section>
    <Card />
  </section>

  <!-- <Clients /> -->
  <section><Footer /></section>
</template>

<script setup>
const SERVICES = [
  {
    title: "WRM Digitalisation",
    description:
      "Our professionals have a thorough understanding of the fundamental physical and mathematical concepts that control many engineering challenges, we apply many of these principles in the development of specialized business intelligent software to address some of these issues for energy providers.",
    link: "/wrm-digitalisation",
    image: "/images/eng3.jpg",
  },
  {
    title: "Integrated Asset Mangement",
    description:
      "Our IAM services leverage latest technology and digital oilfield solutions to improve traditional asset management processes across the value chain (reservoir to sales point) in order to reduce cost, increase production, improve HSE and optimise processes",
    link: "/integrated-asset-management",
    image: "/images/assests.jpg",
  },
  {
    title: "E & P Enterprise Planning",
    description:
      "Our professionals have a thorough understanding of the fundamental physical and mathematical concepts that control many engineering challenges, we apply many of these principles in the development of specialized business intelligent software to address some of these issues for energy providers.",
    link: "/ep-enterprise-planning",
    image: "/images/e&p.png",
  },
  {
    title: "Low & Zero Carbon",
    description:
      "We are committed to working with industries, institutions, and government to identify and deploy cost-effective strategies and digital solutions to achieving net-zero emission operations",
    link: "/low-and-zero-carbon",
    image: "/images/low.png",
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
    url("/images/refinery.jpg") no-repeat 50% 50% / cover;
}
.explore-btn {
  border: 0;
  background-image: linear-gradient(to bottom, var(--tw-gradient-stops));
  --tw-gradient-from: #4a0bd2;
  --tw-gradient-stops: var(--tw-gradient-from),
    var(--tw-gradient-to, rgba(185, 34, 39, 0));
  --tw-gradient-to: #4a0bd2;
  text-transform: uppercase;
  --tw-text-opacity: 1;
  @apply py-3 px-6 border-b-2 font-medium mt-7 rounded-full;
}

.solutions {
  height: 25em;
  @apply pt-12 pb-20;
  background: linear-gradient(
      to bottom,
      rgba(5, 24, 62, 0.8),
      rgba(5, 24, 62, 0.2)
    ),
    url("~/assets/images/abstract-bg.webp") no-repeat 50% 50% / cover;
}
@media (min-width: 768px) {
  .solutions {
    height: 22em;
  }
}
@media (min-width: 1024px) {
  .solutions {
    height: 20em;
  }
}
</style>
