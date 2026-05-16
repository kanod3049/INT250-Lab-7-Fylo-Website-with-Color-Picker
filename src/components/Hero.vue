<script setup>
import imgIntro from "../assets/illustration-intro.png";
import bgCurveLight from "../assets/bg-curvy-light-mode.svg";
import bgCurveDark from "../assets/bg-curvy-dark-mode.svg";
</script>

<template>
  <div class="relative w-full">
    
    <section class="relative text-center px-6 pt-16 pb-48 max-w-3xl mx-auto z-10 sm:px-10 md:px-12 lg:max-w-5xl animate-fade-in">
      <!-- ภาพ Hero Illustration -->
      <img :src="imgIntro" alt="Fylo Secure Location" class="mx-auto w-full max-w-md md:max-w-xl mb-10 object-contain animate-slide-up delay-150" />
      
      <h1 class="text-3xl md:text-4xl font-bold leading-snug mb-6 dark:text-white font-heading animate-fade-in delay-150">All your files in one secure location,<br>accessible anywhere.</h1>
      <p class="text-gray-600 dark:text-gray-300 mb-8 md:text-lg max-w-2xl mx-auto animate-fade-in delay-200">Fylo stores all your most important files in one secure location. Access them wherever you need, share and collaborate with friends family, and co-workers.</p>
      
      <button class="bg-[#65e2d9] hover:bg-[#339ecc] text-black dark:text-white font-bold py-3 px-16 rounded-full transition-all duration-300 shadow-lg focus:outline-none w-full md:w-auto hover:-translate-y-0.5 transform animate-pop">
        Get Started
      </button>
    </section>

    <img :src="bgCurveLight" class="block dark:hidden absolute bottom-0 left-0 w-full z-0" aria-hidden="true" alt="" />
    <img :src="bgCurveDark" class="hidden dark:block absolute bottom-0 left-0 w-full z-0" aria-hidden="true" alt="" />
  </div>
</template>

<style scoped></style>