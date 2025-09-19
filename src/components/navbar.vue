<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import logo from '../assets/logo-rc.png'

const open = ref(false)

// chiudi cliccando fuori
const menuRef = ref(null)
function onDocClick(e) {
  if (open.value && menuRef.value && !menuRef.value.contains(e.target)) {
    open.value = false
  }
}
onMounted(() => document.addEventListener('click', onDocClick))
onBeforeUnmount(() => document.removeEventListener('click', onDocClick))
</script>

<template>
  <!-- Navbar sopra tutto -->
  <nav class="fixed top-0 left-0 right-0 bg-cyan-500 text-white z-50">
    <div class="flex justify-between items-center pr-6 py-4 max-w-7xl mx-auto">
      <!-- logo vicino al bordo sx -->
      <img :src="logo" alt="Logo RC" class="h-8 ml-2" />

      <!-- Menu -->
      <ul class="flex items-center gap-8 text-lg">
        <li>
          <a href="#about" class="hover:underline underline-offset-4">About me</a>
        </li>

        <!-- Wrapper con ref per click-outside -->
        <li class="relative" ref="menuRef">
          <button
            @click="open = !open"
            @keydown.escape="open = false"
            class="hover:underline underline-offset-4 flex items-center gap-1 focus:outline-none"
            aria-haspopup="menu"
            :aria-expanded="open"
          >
            Projects
            <svg :class="open ? 'rotate-180' : ''" class="w-4 h-4 transition-transform" viewBox="0 0 20 20" fill="currentColor">
              <path fill-rule="evenodd" d="M5.23 7.21a.75.75 0 0 1 1.06.02L10 10.94l3.71-3.71a.75.75 0 1 1 1.06 1.06l-4.24 4.24a.75.75 0 0 1-1.06 0L5.21 8.29a.75.75 0 0 1 .02-1.08z" clip-rule="evenodd"/>
            </svg>
          </button>

          <!-- Dropdown: solo a click -->
          <transition
            enter-active-class="transition duration-150 ease-out"
            enter-from-class="opacity-0 translate-y-1"
            enter-to-class="opacity-100 translate-y-0"
            leave-active-class="transition duration-100 ease-in"
            leave-from-class="opacity-100 translate-y-0"
            leave-to-class="opacity-0 translate-y-1"
          >
            <div v-show="open" class="absolute left-0 top-full mt-3 z-[60]">
              <ul
                class="min-w-[200px] rounded-2xl border border-white/15 bg-black/30 backdrop-blur-md
                       text-white shadow-lg overflow-hidden"
                role="menu"
              >
                <li><a href="#web-design"     class="block px-4 py-2 hover:bg-white/10" role="menuitem" @click="open=false">Web design</a></li>
                <li><a href="#brand-design"   class="block px-4 py-2 hover:bg-white/10" role="menuitem" @click="open=false">Brand Design</a></li>
                <li><a href="#product-design" class="block px-4 py-2 hover:bg-white/10" role="menuitem" @click="open=false">Product Design</a></li>
              </ul>
            </div>
          </transition>
        </li>

        <li>
          <a href="#contact" class="hover:underline underline-offset-4">Contact</a>
        </li>
      </ul>
    </div>
  </nav>
</template>
