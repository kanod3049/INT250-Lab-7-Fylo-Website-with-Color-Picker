<script setup>
import { ref } from "vue";

const email = ref("");
const message = ref("");

const submitForm = () => {
  if(email.value) {
    message.value = "Success! We have received your request.";
    email.value = "";
    setTimeout(() => { message.value = ""; }, 4000);
  }
};
</script>

<template>
  <section class="max-w-4xl mx-auto px-6 relative translate-y-1/2 z-50 animate-fade-in delay-150">
    <div class="bg-white dark:bg-[#1c2431] p-10 md:p-10 lg:p-12 rounded-xl shadow-2xl text-center dark:text-white border border-gray-100 dark:border-none relative">
      <h2 class="text-2xl md:text-3xl font-bold mb-4 font-heading">Get early access today</h2>
      <p class="text-gray-600 dark:text-gray-300 mb-8 max-w-2xl mx-auto text-sm md:text-base">It only takes a minute to sign up and our free starter tier is extremely generous. If you have any questions, our support team would be happy to help you.</p>
      
      <form class="flex flex-col md:flex-row gap-4 md:gap-6 max-w-2xl mx-auto" @submit.prevent="submitForm">
        <input 
          type="email" 
          v-model="email"
          placeholder="email@example.com" 
          class="flex-1 px-6 py-4 rounded-full text-black bg-gray-100 focus:outline-none focus:ring-2 focus:ring-[#65e2d9] transition-shadow w-full" 
          required 
          aria-label="Email Address"
        />
        <button type="submit" class="bg-[#65e2d9] hover:bg-[#339ecc] text-black dark:text-white font-bold py-4 px-8 rounded-full transition-all duration-300 w-full md:w-auto shadow-lg shrink-0 hover:-translate-y-0.5 transform">
          Get Started For Free
        </button>
      </form>
      
      <p v-if="message" class="text-green-500 mt-4 text-sm font-bold">{{ message }}</p>
    </div>
  </section>
</template>

<style scoped></style>