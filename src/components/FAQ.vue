<script setup>
import { ref } from "vue";

const activeIndex = ref(null);

const faqs = ref([
  { question: 'What is Fylo?', answer: 'Fylo is a cloud storage service that allows you to store your files in a secure location and access them from anywhere. It offers seamless integration across your devices.' },
  { question: 'How can I share files with others?', answer: 'You can generate shareable links for individual files or entire folders. You can also invite users via email to view or edit specific content.' },
  { question: 'Is my data safe with Fylo?', answer: 'Yes! We use military-grade encryption to ensure your files are safe both in transit and at rest. Additionally, we support 2-factor authentication for added security.' },
  { question: 'What forms of payment do you accept?', answer: 'We accept all major credit cards, PayPal, and Apple Pay. For enterprise plans, we can arrange invoice payments.' }
]);

const toggleFaq = (index) => {
  activeIndex.value = activeIndex.value === index ? null : index;
};
</script>

<template>
  <!-- กำหนดสีพื้นหลังให้กว้างเต็มจอที่ section -->
  <section id="faq" class="w-full bg-white dark:bg-[#181f2a] transition-colors duration-300">
    <div class="max-w-4xl mx-auto px-6 py-20 sm:px-10 md:px-12">
      
      <h2 class="text-3xl font-bold text-center mb-6 dark:text-white font-heading">Frequently Asked Questions</h2>
      <p class="text-center text-gray-600 dark:text-gray-300 mb-10">Here are some of our FAQs. If you have any other questions you'd like answered please feel free to email us.</p>
      
      <div class="space-y-2">
        <div v-for="(item, index) in faqs" :key="index" class="border-b border-gray-300 dark:border-gray-700">
          <button 
            @click="toggleFaq(index)" 
            class="flex justify-between items-center w-full py-5 text-left font-bold text-sm md:text-base hover:text-[#65e2d9] dark:hover:text-[#65e2d9] transition-colors dark:text-gray-200 focus:outline-none"
            :aria-expanded="activeIndex === index"
          >
            {{ item.question }}
            <svg class="w-5 h-5 text-black dark:text-white transition-transform duration-300" :class="activeIndex === index ? 'rotate-180' : ''" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
          </button>
          
          <div v-show="activeIndex === index" class="pb-6 text-gray-600 dark:text-gray-400 text-sm md:text-base leading-relaxed transition-all duration-300 ease-out">
            {{ item.answer }}
          </div>
        </div>
      </div>
      
    </div>
  </section>
</template>

<style scoped></style>