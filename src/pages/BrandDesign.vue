<template>
  <section class="pt-32 max-w-6xl mx-auto px-4 pb-20">
    <h1 class="text-5xl font-extrabold mb-2 text-white">Projects</h1>
    <h2 class="text-2xl font-bold text-cyan-400 mb-12">Brand Design</h2>
    <div class="flex flex-col gap-16 items-center">
      <!-- Card Rebert streetwear -->
      <div class="bg-white/10 backdrop-blur-xl border border-cyan-400 rounded-3xl shadow-2xl flex flex-col items-center py-10 px-6 w-full max-w-3xl transition duration-300 hover:scale-105 hover:shadow-cyan-400/30 animate-fadein">
        <img src="../assets/rebert.png" alt="Rebert streetwear" class="w-full h-[340px] rounded-2xl object-cover mb-6 transition duration-300 hover:shadow-lg" />
        <span class="text-white text-2xl font-bold text-center mt-2">Rebert streetwear</span>
      </div>
      <!-- Card Piadina Roberto Concept -->
      <div class="bg-white/10 backdrop-blur-xl border border-cyan-400 rounded-3xl shadow-2xl flex flex-col items-center py-10 px-6 w-full max-w-3xl transition duration-300 hover:scale-105 hover:shadow-cyan-400/30 animate-fadein">
        <img src="../assets/piadinaroberto.png" alt="Rebranding piadine Roberto Concept" class="w-full h-[340px] rounded-2xl object-cover mb-6 transition duration-300 hover:shadow-lg" />
        <span class="text-white text-2xl font-bold text-center mt-2">Rebranding piadine Roberto Concept</span>
      </div>
      <!-- Card Iron Riff -->
      <div class="bg-white/10 backdrop-blur-xl border border-cyan-400 rounded-3xl shadow-2xl flex flex-col items-center py-10 px-6 w-full max-w-3xl transition duration-300 hover:scale-105 hover:shadow-cyan-400/30 animate-fadein">
        <img src="../assets/ironriff.png" alt="Iron Riff" class="w-full h-[340px] rounded-2xl object-cover mb-6 transition duration-300 hover:shadow-lg" />
        <span class="text-white text-2xl font-bold text-center mt-2">Iron Riff</span>
      </div>
    </div>
  </section>
</template>

<script setup>
import rebert from '../assets/rebert.png';
import piadinaroberto from '../assets/piadinaroberto.png';
import ironriff from '../assets/ironriff.png';

const cards = [
  {
    img: rebert,
    title: 'Rebert streetwear',
  },
  {
    img: piadinaroberto,
    title: 'Rebranding piadine Roberto Concept',
  },
  {
    img: ironriff,
    title: 'Iron Riff',
  },
];
</script>

<style scoped>
@keyframes zoomin {
  0% {
    opacity: 0;
    transform: scale(0.7);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}
.animate-fadein {
  animation: zoomin 0.8s cubic-bezier(.4,0,.2,1);
}
</style>
