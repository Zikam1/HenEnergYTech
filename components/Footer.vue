<template>
  <footer class="bg-gray-900 text-white py-8 mt-24">
    <div class="container mx-auto px-4 md:px-8 lg:px-16 xl:px-20">
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6 md:gap-12">
        <div class="animate-fade-in-up delay-150">
          <h3 class="text-xl font-semibold mb-2">Cyphercrescent Group</h3>
          <p class="text-sm mb-4">Core Values</p>
          <p class="text-sm mb-4">Case Studies</p>
          <p class="text-sm mb-4">Company News</p>
          <p class="text-sm mb-4">Case Studies</p>
        </div>
        <div class="animate-fade-in-up delay-300">
          <h3 class="text-xl font-semibold mb-2">Services</h3>
          <ul class="text-sm">
            <li class="mb-2"><a href="#">Sepal WRMS</a></li>
            <li class="mb-2">
              <a href="#">Sepal BFS</a>
            </li>
            <li class="mb-2"><a href="#">Sepal DIAP</a></li>
            <li class="mb-2"><a href="#">Sepal IDS</a></li>
            <li class="mb-2"><a href="#">EAGLE GAZE WIMS</a></li>
          </ul>
        </div>
        <div class="animate-fade-in-up delay-450">
          <h3 class="text-xl font-semibold mb-2">Contact Us</h3>
          <p class="text-sm mb-2">Linkeldln</p>
          <p class="text-sm mb-2">Twitter</p>
          <p class="text-sm">Youtube</p>
        </div>
      </div>
      <div class="mt-8 text-center animate-fade-in-up delay-600">
        <p class="text-sm">&copy; {{ currentYear }} @ CypherCrescent 2023</p>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      currentYear: new Date().getFullYear(),
    };
  },
};
</script>

<style scoped>
@keyframes fade-in-up {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}
.animate-fade-in-up {
  animation: fade-in-up 0.8s ease-out;
}

.delay-150 {
  animation-delay: 150ms;
}

.delay-300 {
  animation-delay: 300ms;
}

.delay-450 {
  animation-delay: 450ms;
}

.delay-600 {
  animation-delay: 600ms;
}

@media (min-width: 768px) {
  .grid-cols-1 {
    grid-template-columns: repeat(1, minmax(0, 1fr));
  }
}

@media (min-width: 1024px) {
  .grid-cols-1 {
    grid-template-columns: repeat(3, minmax(0, 1fr));
  }
}
</style>
