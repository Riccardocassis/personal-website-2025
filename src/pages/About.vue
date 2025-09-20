<template>
  <section class="pt-32 max-w-5xl mx-auto px-6 relative">
  <h1 class="text-6xl font-extrabold mb-14 tracking-tight text-white drop-shadow-lg">About me</h1>
    <div class="flex flex-col md:flex-row gap-8 md:gap-16 mb-16 max-w-2xl mx-auto text-center md:text-left">
      <p class="text-white/90 text-lg leading-relaxed drop-shadow-sm">
        Ho sempre nutrito una forte passione per i computer e per il mondo della creatività in tutte le sue espressioni. Amo mettermi continuamente alla prova e lavorare a stretto contatto con le persone. La curiosità e il desiderio di apprendere da nuove esperienze sono la mia principale fonte di energia e la bussola che orienta le mie scelte.
      </p>
      <p class="text-white/90 text-lg leading-relaxed drop-shadow-sm">
        Ritengo che il Design non sia soltanto una disciplina fine a se stessa, ma una forma mentis applicabile nei campi più disparati e in ogni sfaccettatura della vita. Progettare per me è come un gioco di strategia, durante il quale coniugo creatività e analisi tecnica delle problematiche per arrivare al processo che mi porta alla soluzione.
      </p>
    </div>
    <div class="w-full flex flex-col items-center justify-center mt-16">
      <!-- Desktop: immagini ai lati -->
      <div class="fixed left-0 bottom-0 w-[38vw] min-w-[320px] max-w-none z-0 hidden md:block">
        <img src="../assets/ioartista.png" alt="Artista" class="w-full object-contain opacity-70 transition duration-300" />
      </div>
      <div class="fixed right-0 bottom-0 w-[38vw] min-w-[320px] max-w-none z-0 hidden md:block">
        <img src="../assets/ionerd.png" alt="Nerd" class="w-full object-contain opacity-70 transition duration-300" />
      </div>
      <!-- Mobile: una sola foto sotto il titolo -->
      <div class="block md:hidden w-full flex justify-center mb-6">
        <img src="../assets/ioartista.png" alt="Artista" class="w-[70vw] max-w-xs object-contain opacity-70" />
      </div>
      <div class="relative w-full h-[400px] mt-2 z-10 flex items-center justify-center">
        <h2 class="w-full text-4xl md:text-5xl font-bold text-cyan-400 flex justify-center items-center tracking-tight drop-shadow-lg transition duration-300 text-center">Il Giusto mix tra artista e nerd.</h2>
      </div>
    </div>
  </section>
</template>