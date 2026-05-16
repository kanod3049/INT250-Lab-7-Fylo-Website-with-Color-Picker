<script setup>
import Navbar from './components/Navbar.vue';
import Hero from './components/Hero.vue';
import Features from './components/Features.vue';
import Productive from './components/Productive.vue';
import FAQ from './components/FAQ.vue';
import Testimonial from './components/Testimonial.vue';
import EarlyAccess from './components/EarlyAccess.vue';
import Footer from './components/Footer.vue';
</script>

<template>
  <div class="min-h-screen text-slate-800 dark:text-gray-200 font-sans transition-colors duration-300 relative">
    
    <div class="bg-white dark:bg-[#1c2431] relative z-10">
      <Navbar />
      <Hero />
    </div>

    <main class="relative z-20 bg-[#f8f9fe] dark:bg-[#181f2a]">
      <Features />
      <Productive />
      <FAQ />
      <Testimonial />
      <EarlyAccess />
    </main>
    
    <Footer />
  </div>
</template>

<style scoped></style>