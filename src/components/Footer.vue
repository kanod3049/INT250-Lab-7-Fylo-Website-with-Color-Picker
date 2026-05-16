<script setup>
import logoDark from "../assets/logo-dark-mode.svg";
import iconPhone from "../assets/icon-phone.svg";
import iconEmail from "../assets/icon-email.svg";
import iconFacebook from "../assets/facebook.svg";
import iconTwitter from "../assets/twitter.svg";
import iconInstagram from "../assets/instagram.svg";

const contactInfo = [
  { icon: iconPhone, text: '+1-543-123-4567', alt: 'Phone' },
  { icon: iconEmail, text: 'example@fylo.com', alt: 'Email' }
];

const menuLinks1 = ['About Us', 'Jobs', 'Press', 'Blog'];
const menuLinks2 = ['Contact Us', 'Terms', 'Privacy'];

const socialLinks = [
  { name: 'Facebook', icon: iconFacebook, url: '#' },
  { name: 'Twitter', icon: iconTwitter, url: '#' },
  { name: 'Instagram', icon: iconInstagram, url: '#' }
];
</script>

<template>
  <footer class="bg-[#0b1523] pt-80 pb-16 px-6 text-white relative z-10">
    <div class="max-w-7xl mx-auto">
      
      <div class="flex flex-col md:flex-row justify-between gap-10 md:gap-6 text-sm text-gray-300 items-start">
    
        <div class="space-y-4 md:w-1/3">
          <p v-for="(item, index) in contactInfo" :key="index" class="flex items-center gap-4">
            <img :src="item.icon" :alt="item.alt" class="w-5 h-5 brightness-0 invert" /> 
            {{ item.text }}
          </p>
        </div>

        <div class="flex flex-col sm:flex-row gap-10 md:gap-10 lg:gap-24 md:w-1/3 justify-center">
          <div class="flex flex-col gap-4">
            <a v-for="(link, index) in menuLinks1" :key="'menu1-'+index" href="#" class="hover:text-[#65e2d9] transition-colors focus:outline-none w-max">
              {{ link }}
            </a>
          </div>

          <div class="flex flex-col gap-4">
            <a v-for="(link, index) in menuLinks2" :key="'menu2-'+index" href="#" class="hover:text-[#65e2d9] transition-colors focus:outline-none w-max">
              {{ link }}
            </a>
          </div>
        </div>
      
        <div class="w-full md:w-1/3 flex justify-center md:justify-end gap-4 mt-8 md:mt-0">
          <a 
            v-for="(social, index) in socialLinks" 
            :key="index" 
            :href="social.url" 
            :aria-label="social.name"
            class="w-8 h-8 bg-[#1c2431] rounded-full flex items-center justify-center hover:bg-[#65e2d9] transition-colors group focus:outline-none shrink-0"
          >
             <img :src="social.icon" class="w-4 h-4 brightness-0 invert group-hover:brightness-100 transition-all" :alt="social.name" />
          </a>
        </div>
        
      </div>
    </div>
  </footer>
</template>

<style scoped></style>