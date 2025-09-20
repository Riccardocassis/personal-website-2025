<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import { RouterLink } from 'vue-router'
import logo from '../assets/logo-rc.png'

const openDesktop = ref(false)      // dropdown desktop
const mobileOpen = ref(false)       // menu mobile
const mobileProjects = ref(false)   // accordion Projects nel mobile

// Chiudi dropdown desktop cliccando fuori
const desktopRef = ref(null)
function onDocClick(e) {
  if (openDesktop.value && desktopRef.value && !desktopRef.value.contains(e.target)) {
    openDesktop.value = false
  }
}
// Chiudi mobile con ESC
function onKeydown(e) {
  if (e.key === 'Escape') {
    mobileOpen.value = false
    openDesktop.value = false
  }
}
onMounted(() => {
  document.addEventListener('click', onDocClick)
  document.addEventListener('keydown', onKeydown)
})
onBeforeUnmount(() => {
  document.removeEventListener('click', onDocClick)
  document.removeEventListener('keydown', onKeydown)
})
</script>

<template>
  <!-- fissa sopra -->
  <nav class="fixed top-0 left-0 right-0 bg-cyan-500 text-white z-50">
    <div class="flex items-center justify-between py-4 max-w-7xl mx-auto w-full px-3 sm:px-4 md:px-6">
      <!-- Logo vicino al bordo sx -->
      <RouterLink to="/">
        <img :src="logo" alt="Logo RC" class="h-8" />
      </RouterLink>

      <!-- Desktop menu -->
      <ul class="hidden md:flex items-center gap-8 text-lg">
        <li>
          <RouterLink to="/about" class="hover:underline underline-offset-4">
            About me
          </RouterLink>
        </li>

        <!-- Dropdown desktop -->
        <li class="relative" ref="desktopRef">
          <button
            @click="openDesktop = !openDesktop"
            class="hover:underline underline-offset-4 flex items-center gap-1 focus:outline-none"
            aria-haspopup="menu"
            :aria-expanded="openDesktop"
          >
            Projects
            <svg :class="openDesktop ? 'rotate-180' : ''" class="w-4 h-4 transition-transform" viewBox="0 0 20 20" fill="currentColor">
              <path fill-rule="evenodd" d="M5.23 7.21a.75.75 0 0 1 1.06.02L10 10.94l3.71-3.71a.75.75 0 1 1 1.06 1.06l-4.24 4.24a.75.75 0 0 1-1.06 0L5.21 8.29a.75.75 0 0 1 .02-1.08z" clip-rule="evenodd"/>
            </svg>
          </button>

          <transition
            enter-active-class="transition duration-150 ease-out"
            enter-from-class="opacity-0 translate-y-1"
            enter-to-class="opacity-100 translate-y-0"
            leave-active-class="transition duration-100 ease-in"
            leave-from-class="opacity-100 translate-y-0"
            leave-to-class="opacity-0 translate-y-1"
          >
            <div v-show="openDesktop" class="absolute left-0 top-full mt-3 z-[60]">
              <ul
                class="min-w-[220px] rounded-2xl border border-white/15 bg-black/30 backdrop-blur-md
                       text-white shadow-lg overflow-hidden"
                role="menu"
              >
                <li>
                  <RouterLink to="/projects/web" class="block px-4 py-2 hover:bg-white/10" @click="openDesktop=false">
                    Web design
                  </RouterLink>
                </li>
                <li>
                  <RouterLink to="/projects/brand" class="block px-4 py-2 hover:bg-white/10" @click="openDesktop=false">
                    Brand Design
                  </RouterLink>
                </li>
                <li>
                  <RouterLink to="/projects/product" class="block px-4 py-2 hover:bg-white/10" @click="openDesktop=false">
                    Product Design
                  </RouterLink>
                </li>
              </ul>
            </div>
          </transition>
        </li>

        <li>
          <RouterLink to="/contact" class="hover:underline underline-offset-4">
            Contact
          </RouterLink>
        </li>
      </ul>

      <!-- Burger (mobile) -->
      <button
        class="md:hidden inline-flex items-center justify-center w-10 h-10 rounded-lg hover:bg-cyan-400/30 focus:outline-none"
        @click="mobileOpen = !mobileOpen"
        aria-label="Open menu"
        :aria-expanded="mobileOpen"
      >
        <svg v-if="!mobileOpen" class="w-6 h-6" viewBox="0 0 24 24" fill="none" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
        </svg>
        <svg v-else class="w-6 h-6" viewBox="0 0 24 24" fill="none" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
        </svg>
      </button>
    </div>

    <!-- Mobile menu panel -->
    <transition
      enter-active-class="transition duration-150 ease-out"
      enter-from-class="opacity-0 -translate-y-2"
      enter-to-class="opacity-100 translate-y-0"
      leave-active-class="transition duration-100 ease-in"
      leave-from-class="opacity-100 translate-y-0"
      leave-to-class="opacity-0 -translate-y-2"
    >
      <div
        v-show="mobileOpen"
        class="md:hidden bg-cyan-500/95 backdrop-blur-sm text-white border-t border-white/10"
      >
        <div class="px-4 py-3 space-y-2">
          <RouterLink to="/about" class="block px-2 py-2 rounded hover:bg-white/10" @click="mobileOpen=false">
            About me
          </RouterLink>

          <!-- accordion Projects -->
          <div class="rounded">
            <button
              class="w-full flex items-center justify-between px-2 py-2 rounded hover:bg-white/10"
              @click="mobileProjects = !mobileProjects"
            >
              <span>Projects</span>
              <svg :class="mobileProjects ? 'rotate-180' : ''" class="w-4 h-4 transition-transform" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M5.23 7.21a.75.75 0 0 1 1.06.02L10 10.94l3.71-3.71a.75.75 0 1 1 1.06 1.06l-4.24 4.24a.75.75 0 0 1-1.06 0L5.21 8.29a.75.75 0 0 1 .02-1.08z" clip-rule="evenodd"/>
              </svg>
            </button>

            <transition
              enter-active-class="transition duration-150 ease-out"
              enter-from-class="opacity-0 -translate-y-1"
              enter-to-class="opacity-100 translate-y-0"
              leave-active-class="transition duration-100 ease-in"
              leave-from-class="opacity-100 translate-y-0"
              leave-to-class="opacity-0 -translate-y-1"
            >
              <div v-show="mobileProjects" class="mt-1 ml-2 space-y-1">
                <RouterLink to="/projects/web" class="block px-3 py-2 rounded hover:bg-white/10" @click="mobileOpen=false">
                  Web design
                </RouterLink>
                <RouterLink to="/projects/brand" class="block px-3 py-2 rounded hover:bg-white/10" @click="mobileOpen=false">
                  Brand Design
                </RouterLink>
                <RouterLink to="/projects/product" class="block px-3 py-2 rounded hover:bg-white/10" @click="mobileOpen=false">
                  Product Design
                </RouterLink>
              </div>
            </transition>
          </div>

          <RouterLink to="/contact" class="block px-2 py-2 rounded hover:bg-white/10" @click="mobileOpen=false">
            Contact
          </RouterLink>
        </div>
      </div>
    </transition>
  </nav>
</template>