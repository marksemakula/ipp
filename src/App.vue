<template>
  <div class="app">
    <Hero />
    <Partners />
    <Contact />
    <Footer />
  </div>
</template>

<script setup lang="ts">
import Hero from './components/Hero.vue'
import Partners from './components/Partners.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'
</script>

<style scoped>
.app {
  width: 100%;
  overflow-x: hidden;
}
</style>
