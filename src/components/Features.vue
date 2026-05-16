<script setup>
import { ref } from "vue";
import iconAccess from "../assets/icon-access-anywhere.svg";
import iconSecurity from "../assets/icon-security.svg";
import iconCollaboration from "../assets/icon-collaboration.svg";
import iconAnyFile from "../assets/icon-any-file.svg";


const features = ref([
  { 
    icon: iconAccess, 
    title: 'Access your files, anywhere', 
    desc: 'The ability to use a smartphone, tablet, or computer to access your account means your files follow you everywhere.' 
  },
  { 
    icon: iconSecurity, 
    title: 'Security you can trust', 
    desc: '2-factor authentication and user-controlled encryption are just a couple of the security features we allow to help secure your files.' 
  },
  { 
    icon: iconCollaboration, 
    title: 'Real-time collaboration', 
    desc: 'Securely share files and folders with friends, family and colleagues for live collaboration. No email attachments required.' 
  },
  { 
    icon: iconAnyFile, 
    title: 'Store any file', 
    desc: 'Whether you\'re sharing holidays photos or work documents, Fylo has you covered allowing for all file types to be securely stored and shared.' 
  }
]);
</script>

<template>
  <section id="features" class="grid grid-cols-1 md:grid-cols-2 gap-16 max-w-5xl mx-auto px-6 py-20 text-center relative z-10 sm:px-10 md:px-12">
    <div v-for="(feature, index) in features" :key="index" class="flex flex-col items-center px-4 sm:px-6 animate-fade-in hover:-translate-y-1 transition-transform duration-300 delay-150">
      <img :src="feature.icon" :alt="feature.title" class="mb-6 h-20 object-contain" />
      <h3 class="text-xl font-bold mb-3 dark:text-white font-heading">{{ feature.title }}</h3>
      <p class="text-gray-600 dark:text-gray-300 text-sm max-w-sm">{{ feature.desc }}</p>
    </div>
  </section>
</template>

<style scoped></style>