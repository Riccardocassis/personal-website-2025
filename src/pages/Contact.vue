<template>
  <section class="pt-32 max-w-3xl mx-auto px-4 pb-20 flex flex-col items-center">
    <h1 class="text-5xl font-extrabold mb-6 text-white">Per maggiori informazioni</h1>
    <h2 class="text-2xl font-bold text-cyan-400 mb-10">Scrivimi qui</h2>
    <div class="bg-white/10 backdrop-blur-xl border border-cyan-400 rounded-3xl shadow-2xl w-full max-w-xl px-8 py-10 flex flex-col items-center gap-6 morphic-contact animate-fadein">
      <form class="w-full flex flex-col gap-5">
        <input type="text" placeholder="Nome" class="bg-black/40 border border-cyan-400 rounded-xl px-4 py-3 text-white placeholder-cyan-300 focus:outline-none focus:ring-2 focus:ring-cyan-400 transition" />
        <input type="email" placeholder="Email" class="bg-black/40 border border-cyan-400 rounded-xl px-4 py-3 text-white placeholder-cyan-300 focus:outline-none focus:ring-2 focus:ring-cyan-400 transition" />
        <textarea placeholder="Messaggio" rows="4" class="bg-black/40 border border-cyan-400 rounded-xl px-4 py-3 text-white placeholder-cyan-300 focus:outline-none focus:ring-2 focus:ring-cyan-400 transition"></textarea>
        <button type="submit" class="bg-cyan-400 text-black font-bold rounded-xl px-6 py-3 mt-2 hover:bg-cyan-500 transition">Invia</button>
      </form>
    </div>
  </section>
  <Footer />
</template>
<script setup>
import Footer from '../components/Footer.vue'
</script>

<style scoped>
@keyframes fadein {
  0% {
    opacity: 0;
    transform: scale(0.8);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}
.animate-fadein {
  animation: fadein 0.8s cubic-bezier(.4,0,.2,1);
}
.morphic-contact {
  box-shadow: 0 8px 32px 0 rgba(0,0,0,0.37);
  backdrop-filter: blur(16px);
  -webkit-backdrop-filter: blur(16px);
  border: 1.5px solid rgba(80, 200, 255, 0.25);
  background: rgba(30, 41, 59, 0.55);
}
</style>