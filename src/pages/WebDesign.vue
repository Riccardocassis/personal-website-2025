<template>
  <section class="pt-32 max-w-6xl mx-auto px-4 pb-20">
    <h1 class="text-5xl font-extrabold mb-2 text-white">Projects</h1>
    <h2 class="text-2xl font-bold text-cyan-400 mb-12">Web Design</h2>
  <div class="flex flex-col gap-16 items-center">
      <!-- Card Fill-bo -->
  <div class="bg-white/10 backdrop-blur-xl border border-cyan-400 rounded-3xl shadow-2xl flex flex-col items-center py-10 px-6 w-full max-w-3xl transition duration-300 hover:scale-105 hover:shadow-cyan-400/30 animate-fadein">
        <img src="../assets/fillbo.png" alt="Fill-bo" class="w-full h-[340px] rounded-2xl object-cover mb-6 transition duration-300 hover:shadow-lg" />
        <span class="text-white text-2xl font-bold text-center mt-2">Fill-bo Refil</span>
      </div>
      <!-- Card Museo della carta -->
  <div class="bg-white/10 backdrop-blur-xl border border-cyan-400 rounded-3xl shadow-2xl flex flex-col items-center py-10 px-6 w-full max-w-3xl transition duration-300 hover:scale-105 hover:shadow-cyan-400/30 animate-fadein">
        <img src="../assets/museodellacarta.png" alt="Museo della carta" class="w-full h-[340px] rounded-2xl object-cover mb-6 transition duration-300 hover:shadow-lg" />
        <span class="text-white text-2xl font-bold text-center mt-2">Museo della carta new concept</span>
      </div>
      <!-- Card Interactive guitar -->

      <div class="bg-white/10 backdrop-blur-xl border border-cyan-400 rounded-3xl shadow-2xl flex flex-col items-center py-10 px-6 w-full max-w-3xl transition duration-300 hover:scale-105 hover:shadow-cyan-400/30 animate-fadein">
        <img src="../assets/appchitarra.png" alt="Interactive guitar" class="w-full h-[340px] rounded-2xl object-cover mb-6 transition duration-300 hover:shadow-lg" />
        <span class="text-white text-2xl font-bold text-center mt-2">Interactive guitar</span>
      </div>
    </div>
  </section>
</template>

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
.flex-col.items-center {
  flex-direction: column !important;
  align-items: center;
  gap: 2rem;
}
.bg-white\/10 {
  width: 100%;
  max-width: 900px;
  min-width: 0;
}
img {
  margin-bottom: 1rem !important;
  width: 100%;
  height: auto !important;
  max-height: 340px;
  object-fit: contain !important;
  border-radius: 1rem;
  background: #18181b;
}
@media (max-width: 768px) {
  .bg-white\/10 {
    max-width: 100vw;
    min-width: 0;
    height: auto;
  }
  img {
    max-height: 180px;
    margin-bottom: 0.7rem !important;
  }
  .flex-col.items-center {
    gap: 1.2rem;
  }
}
</style>