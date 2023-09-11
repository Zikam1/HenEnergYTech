<template>
  <section
    class="heros relative min-h-[31rem] lg:min-h-[36rem] flex text-white items-center"
  >
    <div class="px-4 sm:px-10 md:px-20">
      <h1 class="text-[2.5rem] leading-[2.5rem] font-semibold">
        Developing Digitalization Solutions
      </h1>
      <p class="mt-[2rem] w-[90%] md:w-[60%] text-base">
        To partner in crafting pioneering technological answers that help
        businesses swiftly integrate sustainable digital practices..
      </p>
    </div>
  </section>
  <Tabs :tabs="tabs" :selected="activeTab" @change="onTabChange" />

  <div class="pb-16">
    <!-- WRM Digitalisation -->

    <div v-if="activeTab === 'WRM Digitalisation'">WRM Digitalisation</div>
    <div v-else-if="activeTab === 'Integrated Asset Management'">
      Integrated Asset Management
    </div>
    <div v-else-if="activeTab === 'Enterprise'">Enterprise</div>
    <div v-else-if="activeTab === 'Low & Zero Carbon'">Low & Zero Carbon</div>
  </div>

  <div class="min-h-screen py-12">
    <div class="container mx-auto">
      <h1 class="text-3xl font-semibold mb-8">Products</h1>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div
          v-for="(product, index) in products"
          :key="index"
          class="bg-white rounded-lg shadow-md p-6"
        >
          <img
            :src="product.image"
            :alt="product.name"
            class="mx-auto h-32 mb-4"
          />
          <h2 class="text-xl font-semibold mb-2">{{ product.name }}</h2>
          <p class="text-gray-600 mb-4">{{ product.description }}</p>
          <div class="flex justify-between items-center">
            <span class="text-lg font-semibold"
              >#{{ product.price.toFixed(2) }}</span
            >
            <button
              @click="addToCart(product)"
              class="px-4 py-4 rounded-lg bg-blue-500 text-white hover:bg-blue-600 focus:outline-none"
            >
              Add
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [
        {
          name: "Product 1",
          description: "wrms    .",
          image: "/product1.jpg",
        },
        {
          name: "Product 2",
          description: "Aenean eget ex nec urna ultrices rhoncus.",
          image: "/product2.jpg",
        },
        {
          name: "Product 3",
          description: "Vivamus commodo sapien vel egestas.",
          image: "/images/eng3.jpg",
        },
      ],
      cart: [],
      tabs: [
        "WRM Digitalisation",
        "Integrated Asset Management",
        "Enterprise",
        "Low & Zero Carbon",
      ],
      activeTab: "WRM Digitalisation",
      isLoading: false,
    };
  },
  methods: {
    addToCart(product) {
      this.cart.push(product);
    },
    onTabChange(tab) {
      this.activeTab = tab;
    },
  },
};
</script>

<style>
.bg-gray-100 {
  background-color: #f4f4f4;
}

.heros {
  background: linear-gradient(
      90deg,
      rgba(0, 0, 0, 0.8),
      rgba(0, 0, 0, 0.6),
      rgba(0, 0, 0, 0.7)
    ),
    url("/images/oil-platform.jpg") no-repeat 50% 50% / cover;
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
</style>
