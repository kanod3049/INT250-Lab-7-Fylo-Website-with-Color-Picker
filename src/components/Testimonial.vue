<script setup>
import { ref } from "vue";
import bgQuotes from "../assets/bg-quotes.png";
import profile1 from "../assets/profile-1.jpg";
import profile2 from "../assets/profile-2.jpg";
import profile3 from "../assets/profile-3.jpg";

const reviews = ref([
  { text: 'Fylo has improved our team productivity by an order of magnitude. Since making the switch our team has become a well-oiled collaboration machine.', name: 'Satish Patel', title: 'Founder & CEO, Huddle', avatar: profile1 },
  { text: 'Fylo has improved our team productivity by an order of magnitude. Since making the switch our team has become a well-oiled collaboration machine.', name: 'Bruce McKenzie', title: 'Founder & CEO, Huddle', avatar: profile2 },
  { text: 'Fylo has improved our team productivity by an order of magnitude. Since making the switch our team has become a well-oiled collaboration machine.', name: 'Iva Boyd', title: 'Founder & CEO, Huddle', avatar: profile3 }
]);
</script>

<template>
  <section id="testimonials" class="relative max-w-6xl mx-auto px-6 py-20 pb-40">
    <img :src="bgQuotes" alt="" aria-hidden="true" class="absolute top-10 left-6 md:-left-2 z-0 w-10 md:w-12 object-contain" />
    
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6 md:gap-4 lg:gap-8 relative z-10 mt-6">
      <div v-for="(review, index) in reviews" :key="index" class="bg-gray-50 shadow-xl dark:shadow-none dark:bg-[#202a3c] p-6 md:p-5 lg:p-8 rounded-lg flex flex-col justify-between animate-fade-in hover:-translate-y-2 transition-transform duration-300 delay-150">
        <p class="text-sm md:text-xs lg:text-sm text-gray-700 dark:text-gray-300 mb-6 leading-relaxed">"{{ review.text }}"</p>
        <div class="flex items-center gap-3 mt-auto">
          <img :src="review.avatar" :alt="review.name" class="w-10 h-10 rounded-full shrink-0" loading="lazy" />
          <div>
            <h4 class="font-bold text-sm md:text-xs lg:text-sm dark:text-white tracking-wide font-heading">{{ review.name }}</h4>
            <p class="text-xs text-gray-500 dark:text-gray-400">{{ review.title }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped></style>