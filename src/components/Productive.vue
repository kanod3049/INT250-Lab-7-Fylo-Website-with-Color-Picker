<script setup>
import imgProductive from "../assets/illustration-stay-productive.png";
import iconArrow from "../assets/icon-arrow.svg";
</script>

<template>
  <section class="w-full bg-white dark:bg-[#181f2a] transition-colors duration-300">
    <!-- ลดระยะห่าง (gap) ระหว่างรูปกับข้อความบน Tablet เพื่อให้จัดหน้าได้สวยงามขึ้น -->
    <div class="flex flex-col md:flex-row items-center gap-12 md:gap-8 lg:gap-12 max-w-6xl mx-auto px-6 py-20">
      
      <div class="w-full md:w-1/2 animate-slide-up delay-150">
        <img :src="imgProductive" alt="Stay productive" class="w-full h-auto max-w-md mx-auto object-contain" />
      </div>
      
      <div class="w-full md:w-1/2 text-left animate-fade-in delay-200">
        <h2 class="text-3xl md:text-2xl lg:text-4xl font-bold mb-6 dark:text-white font-heading">Stay productive,<br>wherever you are</h2>
        <p class="text-gray-600 dark:text-gray-300 mb-4 md:text-sm lg:text-base">Never let location be an issue when accessing your files. Fylo has you covered for all of your file storage needs.</p>
        <p class="text-gray-600 dark:text-gray-300 mb-6 md:text-sm lg:text-base">Securely share files and folders with friends, family and colleagues for live collaboration. No email attachments required.</p>
        
        <a href="#" class="flex items-center gap-2 text-[#65e2d9] border-b border-[#65e2d9] pb-1 w-max hover:text-[#339ecc] hover:border-[#339ecc] transition-colors focus:outline-none">
          See how Fylo works 
          <img :src="iconArrow" alt="" aria-hidden="true" class="w-5 h-5 ml-1 object-contain" />
        </a>
      </div>
      
    </div>
  </section>
</template>

<style scoped></style>