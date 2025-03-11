<template>
  <div class="bg-[#D4EBF8] dark:bg-[#080326] min-h-screen">
    <Navbar />
    <HeroSection />
    <Counter />
    <Services />
  </div>
</template>

<script setup lang="ts">
import { defineAsyncComponent, onMounted } from 'vue'

const Navbar = defineAsyncComponent(() => import('@/components/layout/Navbar.vue'))
const HeroSection = defineAsyncComponent(() => import('@/components/layout/HeroSection.vue'))
const Counter = defineAsyncComponent(() => import('@/components/layout/Counter.vue'))
const Services = defineAsyncComponent(() => import('@/components/layout/Services.vue'))

/* //Set default dark mode if no theme is saved
onMounted(() => {
  const theme = localStorage.getItem('theme')
    if (!theme) {
      //default to dark mode if no theme is saved
    document.documentElement.classList.add('dark')
    localStorage.setItem('theme', 'dark')
  } else if (theme === 'dark') {
    // apply lioght mode if theme is saved as light
    document.documentElement.classList.remove('dark')
  }
})
 */
</script>
