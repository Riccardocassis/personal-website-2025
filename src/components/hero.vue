<template>
  <div class="relative h-screen w-full flex flex-col justify-center items-center text-center text-white">
    <img
      src="../assets/hero-riccardo.png"
      alt="Riccardo"
      class="absolute inset-0 w-full h-full object-cover opacity-60"
    />
    <div class="relative z-10">
      <p class="text-cyan-500 text-lg">Hi I’m</p>
      <h1 class="text-5xl md:text-6xl font-bold mt-2">Riccardo Cassis</h1>
      <p class="text-cyan-500 text-xl md:text-2xl mt-2">Product and web designer</p>

      <!-- 👇 Icône subito sotto i testi -->
      <socialIcons class="mt-6" />
    </div>
  </div>
</template>

<script setup>
import socialIcons from './socialIcons.vue'
</script>