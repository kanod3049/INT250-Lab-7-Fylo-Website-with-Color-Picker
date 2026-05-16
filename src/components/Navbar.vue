<script setup>
import { ref, onMounted } from "vue";
import logoLight from "../assets/logo-light-mode.svg";
import logoDark from "../assets/logo-dark-mode.svg";

const menuLinks = [
  { name: 'Features', url: '#features' },
  { name: 'FAQs', url: '#faq' },
  { name: 'Testimonials', url: '#testimonials' }
];

const isDark = ref(false);

function applyTheme(value) {
  isDark.value = value;
  document.documentElement.classList.toggle("dark", value);
  localStorage.setItem("color-theme", value ? "dark" : "light");
}

onMounted(() => {
  const savedTheme = localStorage.getItem("color-theme");
  const shouldUseDark =
    savedTheme === "dark" ||
    (savedTheme === null && window.matchMedia("(prefers-color-scheme: dark)").matches);
  applyTheme(shouldUseDark);
});

function toggleTheme() {
  applyTheme(!isDark.value);
}
</script>

<template>
  <header class="container mx-auto pt-12 px-6 flex flex-col md:flex-row justify-between items-center gap-12 md:gap-0">
    
    <a href="#" class="inline-block">
      <img :src="isDark ? logoDark : logoLight" alt="Fylo Logo" class="h-14 sm:h-16 md:h-10 object-contain transition-all" />
    </a>
    
    <div class="flex items-center space-x-6 sm:space-x-10 md:space-x-10 text-base md:text-sm font-heading">
      <a v-for="(link, index) in menuLinks" :key="index" :href="link.url" class="hover:text-[#65e2d9] dark:hover:text-white transition-colors focus:outline-none">
        {{ link.name }}
      </a>
      
      <button
        id="theme-toggle"
        class="text-gray-500 dark:text-gray-400 hover:bg-gray-100 dark:hover:bg-gray-800 focus:outline-none focus:ring-4 focus:ring-gray-200 dark:focus:ring-gray-700 rounded-lg text-sm p-2 md:p-2.5 transition-colors"
        @click="toggleTheme"
        aria-label="Toggle Dark Mode"
      >
        <svg v-if="!isDark" class="w-6 h-6 md:w-5 md:h-5" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path d="M17.293 13.293A8 8 0 016.707 2.707a8.001 8.001 0 1010.586 10.586z"></path></svg>
        <svg v-else class="w-6 h-6 md:w-5 md:h-5" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path d="M10 2a1 1 0 011 1v1a1 1 0 11-2 0V3a1 1 0 011-1zm4 8a4 4 0 11-8 0 4 4 0 018 0zm-.464 4.95l.707.707a1 1 0 001.414-1.414l-.707-.707a1 1 0 00-1.414 1.414zm2.12-10.607a1 1 0 010 1.414l-.706.707a1 1 0 11-1.414-1.414l.707-.707a1 1 0 011.414 0zM17 11a1 1 0 100-2h-1a1 1 0 100 2h1zm-7 4a1 1 0 011 1v1a1 1 0 11-2 0v-1a1 1 0 011-1zM5.05 6.464A1 1 0 106.465 5.05l-.708-.707a1 1 0 00-1.414 1.414l.707.707zm1.414 8.486l-.707.707a1 1 0 01-1.414-1.414l.707-.707a1 1 0 011.414 1.414zM4 11a1 1 0 100-2H3a1 1 0 000 2h1z" fill-rule="evenodd" clip-rule="evenodd"></path></svg>
      </button>
    </div>
    
  </header>
</template>

<style scoped></style>