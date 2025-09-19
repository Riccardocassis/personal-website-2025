<script setup>
import logo from '../assets/logo-rc.png'
</script>

<template>
  <nav class="flex justify-between items-center px-6 py-4 bg-cyan-500 text-white">
    <img :src="logo" alt="Logo RC" class="h-8" />
    <ul class="flex gap-6 text-lg">
      <li><a href="#about">About me</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>
</template>