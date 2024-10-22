<template>
  <div class="min-h-screen py-16 flex flex-col items-center">
    <h2 class="text-5xl font-bold text-center mb-8 text-gray-900 dark:text-white">𝓜𝓮𝓶𝓫𝓮𝓻𝓼 🥤</h2>
    <p class="text-center text-gray-600 dark:text-gray-400 mb-12 font-semibold">
      Meet the talented individuals behind the music.
    </p>

    <!-- Carousel Container -->
    <div class="flex flex-row items-center justify-center w-full max-w-4xl space-x-8">
      <!-- Image Section with Sliding Transition -->
      <div class="w-96 h-96 border-8 border-white rounded-lg overflow-hidden bg-gray-50 shadow-lg shadow-black">
        <transition name="slide" mode="out-in">
          <img 
            :key="currentMemberIndex" 
            :src="members[currentMemberIndex].image" 
            alt="Band member photo" 
            class="w-full h-full object-cover transition-transform duration-500 ease-in-out"
          />
        </transition>
      </div>

      <!-- Member Info Section -->
      <div class="flex flex-col justify-between w-72 space-y-6">
        <div>
          <h3 class="text-3xl font-bold text-gray-800 dark:text-white">
            {{ members[currentMemberIndex].name }}
          </h3>
          <p class="mt-2 text-gray-600 dark:text-gray-400">
            {{ members[currentMemberIndex].description }}
          </p>
        </div>

        <!-- Member Buttons for Carousel Navigation -->
        <div class="flex flex-col space-y-2">
          <button 
            v-for="(member, index) in members" 
            :key="member.name" 
            @click="selectMember(index)"
            :class="{
              'bg-blue-300 text-white': index === currentMemberIndex,
              'bg-white text-black hover:bg-blue-100': index !== currentMemberIndex
            }"
            class="py-2 px-4 rounded-md shadow-md shadow-black transition"
          >
            {{ member.name }}
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

// Import images
import emsImage from '@/assets/img/ems.jpg';
import rovs2Image from '@/assets/img/rovs2.jpg';
import ivonImage from '@/assets/img/ivon.jpg';
import renzImage from '@/assets/img/renz.jpg';
import jungilImage from '@/assets/img/jungil.jpg';

// Band members data with images and descriptions
const members = [
  { 
    name: '𝓔𝓶𝓼 𝓜𝓪𝓻𝔂 𝓣𝓪𝓶𝓹𝓾𝓼', 
    image: emsImage, 
    description: 'Ems brings soulful melodies and charisma to every performance.' 
  },
  { 
    name: '𝓡𝓸𝓿𝓲𝓮 𝓛𝔂𝓷 𝓨𝓬𝓸𝓷𝓰', 
    image: rovs2Image, 
    description: 'Rovie is the heart of rhythm, keeping the music alive.' 
  },
  { 
    name: '𝓘𝓿𝓸𝓷 𝓐𝓻𝓸', 
    image: ivonImage, 
    description: 'Ivon’s energy on stage is infectious and unforgettable.' 
  },
  { 
    name: '𝓡𝓮𝓷𝔃 𝓚𝓪𝔂𝓵𝓮 𝓐𝓷𝓭𝓸', 
    image: renzImage, 
    description: 'Renz delivers powerful guitar solos with passion.' 
  },
  { 
    name: '𝓙𝓾𝓷 𝓖𝓲𝓵 𝓒𝓪𝓼𝓺𝓾𝓮𝓳𝓸', 
    image: jungilImage, 
    description: 'Jun Gil creates a magical atmosphere with his musical talent.' 
  }
];

// Track the current member index
const currentMemberIndex = ref(0);

// Function to update the carousel based on the selected member
function selectMember(index) {
  currentMemberIndex.value = index;
}
</script>

<style scoped>
/* Slide transition styles */
.slide-enter-active, .slide-leave-active {
  transition: transform 0.5s ease;
}

.slide-enter, .slide-leave-to {
  transform: translateX(100%);
}
</style>
