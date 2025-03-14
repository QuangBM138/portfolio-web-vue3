<template>
  <div class="bg-[#D4EBF8] dark:bg-[#080326] min-h-screen">
    <Suspense>
      <template #default>
        <div>
          <Navbar />
          <HeroSection />
          <Counter />
          <Services />
          <Skills />
          <WhyMe />
          <Projects />
          <Contact />
          <Footer />
          <BackToTop />
        </div>
      </template>
      <template #fallback>
        <div class="flex justify-center items-center min-h-screen">
          <LoadingSpinner />
        </div>
      </template>
    </Suspense>

  </div>
</template>

<script setup lang="ts">
import { defineAsyncComponent, onMounted } from 'vue'

const Navbar = defineAsyncComponent(() => import('@/components/layout/Navbar.vue'))
const HeroSection = defineAsyncComponent(() => import('@/components/layout/HeroSection.vue'))
const Counter = defineAsyncComponent(() => import('@/components/layout/Counter.vue'))
const Services = defineAsyncComponent(() => import('@/components/layout/Services.vue'))
const Skills = defineAsyncComponent(() => import('@/components/layout/Skills.vue'))
const WhyMe = defineAsyncComponent(() => import('@/components/layout/WhyMe.vue'))
const Projects = defineAsyncComponent(() => import('@/components/layout/Projects.vue'))
const Contact = defineAsyncComponent(() => import('@/components/layout/Contact.vue'))
const Footer = defineAsyncComponent(() => import('@/components/layout/Footer.vue'))
const BackToTop = defineAsyncComponent(() => import('@/components/layout/BackToTop.vue'))
const LoadingSpinner = defineAsyncComponent(() => import('@/components/layout/LoadingSpinner.vue'))

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

<style>
* {
  scrollbar-width: thin;
  scrollbar-color: #ffffff #2D3748;
}
</style>