<template>
  <Clients />
  <h2
    class="text-2xl sm:text-4xl font-bold mt-20 mb-6 border-l-4 md:border-l-8 pl-3 border-[#b92227]"
  >
    ENERGY TECHNOLOGY
  </h2>

  <div
    class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-y-5 gap-x-32 mb-6"
  >
    <ServiceCard
      v-for="service in SERVICES"
      :key="service.title"
      :service="service"
      :show="false"
    />
  </div>
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
];
</script>
<style></style>
