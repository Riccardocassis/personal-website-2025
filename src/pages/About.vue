<template>
  <div class="h-screen flex flex-col bg-black overflow-hidden">
    <section class="flex-1 flex flex-col justify-center items-center px-8">
      <h1 class="text-6xl font-extrabold mb-8 tracking-tight text-white text-center">About me</h1>
      <div class="max-w-2xl text-white/90 text-lg leading-relaxed mb-8 text-center">
        Ho sempre avuto una grande passione per i computer e per tutto ciò che riguarda la creatività. Mi piace mettermi in gioco, lavorare insieme agli altri e imparare da ogni nuova esperienza.<br>
        Per me il design non è solo una professione, ma un modo di pensare che si può applicare in tanti ambiti diversi.<br>
        Quando progetto lo vivo come una sfida strategica: mescolo creatività e analisi per trasformare un problema in una soluzione.
      </div>
      <h2 class="text-4xl font-bold text-cyan-400 text-center">
        <span>{{ artistaCount }}% Artista</span><br>
        <span>{{ nerdCount }}% Nerd</span>
      </h2>
    </section>
    <!-- Immagini fisse ai lati sopra il footer -->
  <img src="../assets/ioartista.png" alt="Artista" class="fixed left-0 bottom-20 w-[32vw] min-w-[180px] max-w-none object-contain opacity-80 z-10 pointer-events-none" />
  <img src="../assets/ionerd.png" alt="Nerd" class="fixed right-0 bottom-20 w-[32vw] min-w-[180px] max-w-none object-contain opacity-80 z-10 pointer-events-none" />
    <!-- Footer originale statico -->
    <Footer />
  </div>
</template>
<script setup>
import { ref, onMounted } from 'vue'
import Footer from '../components/Footer.vue'

const artistaCount = ref(0)
const nerdCount = ref(0)

function animateCount(target, refVar) {
  let current = 0
  const interval = setInterval(() => {
    if (current < target) {
      current++
      refVar.value = current
    } else {
      clearInterval(interval)
    }
  }, 18)
}

onMounted(() => {
  animateCount(50, artistaCount)
  setTimeout(() => animateCount(50, nerdCount), 400)
})
</script>