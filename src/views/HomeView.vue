<template>
  <section id="home" class="mt-20 flex flex-col md:flex-row items-center w-full p-6">
    <div class="w-full md:w-1/2 p-8">
      <div class="p-8 rounded-md">
        <h1 class="text-black text-4xl md:text-5xl lg:text-6xl font-extrabold tracking-wide animate-fade-up">
          TANAAA UNSAY DUGAYAN ! 🍻
        </h1>
        <p class="text-black mt-4 text-lg md:text-xl">
          Welcome to our website! Join us in celebrating music, friendship, and unforgettable moments.
        </p>
      </div>
    </div>
    <div class="w-full md:w-1/2">
      <video
        ref="videoRef"
        src="../assets/img/intro.mp4"
        alt="Band Image"
        class="lg:w-full h-full object-cover shadow-lg shadow-black"
        @click="toggleVideoPlayback"
        preload="auto"
      />
    </div>
  </section>

  <section id="member" class="dark:bg-gray-900 mt-20 p-6">
    <members />
  </section>

  <section id="gallery" class="bg-white top-0 p-12 dark:bg-gray-900">
    <p class="text-5xl font-bold text-center mb-4">𝓖𝓪𝓵𝓵𝓮𝓻𝔂 🌊</p>
    <p class="text-center text-gray-600">Explore photos from our latest events and performances.</p>
    <gallery/>
  </section>

   <section id="music" class="min-h-screen py-16 p-6">
    <h2 class="text-5xl font-bold text-center mb-8">𝓜𝓾𝓼𝓲𝓬 🎶</h2>
    <p class="text-center text-gray-600">Listen to some of our original tracks and covers.</p>
    <music />
  </section>

  <section id="about" class="min-h-screen dark:bg-gray-900 py-16">
    <h2 class="text-5xl font-bold text-center mb-8 text-gray-900 dark:text-white">𝓐𝓫𝓸𝓾𝓽 𝓤𝓼 ☕</h2>
    <div class="py-16 bg-white">  
  <div class="container m-auto px-6 text-gray-600 md:px-12 xl:px-6">
      <div class="space-y-6 md:space-y-0 md:flex md:gap-6 lg:items-center lg:gap-12">
        <div class="md:5/12 lg:w-5/12">
          <img src="../assets/img/6.jpg" alt="image" class="rounded-full shadow-md shadow-black">
        </div>
        <div class="md:7/12 lg:w-6/12">
          <h2 class="text-2xl text-gray-900 font-bold md:text-4xl">Jam ta bai  is Lorem ipsum dolor sit amet, consectetur adipisicing elit.</h2>
          <p class="mt-6 text-gray-600">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Eum omnis voluptatem accusantium nemo perspiciatis delectus atque autem! Voluptatum tenetur beatae unde aperiam, repellat expedita consequatur! Officiis id consequatur atque doloremque!</p>
          <p class="mt-4 text-gray-600"> Nobis minus voluptatibus pariatur dignissimos libero quaerat iure expedita at? Asperiores nemo possimus nesciunt dicta veniam aspernatur quam mollitia.</p>
        </div>
      </div>
  </div>
</div>
  </section>
  <footer class="bg-white dark:bg-gray-900">
    <div class="container px-6 py-8 mx-auto">
        <div class="flex flex-col items-center text-center">
           <a href="#home" @click.prevent="scrollToSection('#home')">
              𝓙𝓪𝓶 𝓽𝓪 𝓑𝓪𝓲! 🍺
            </a>

            <p class="max-w-md mx-auto mt-4 text-gray-500 dark:text-gray-400">Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>

            <div class="flex flex-col mt-4 sm:flex-row sm:items-center sm:justify-center">

              <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Get Started</button>
            </div>
        </div>

        <hr class="my-10 border-gray-200 dark:border-gray-700" />

        <div class="flex flex-col items-center sm:flex-row sm:justify-between">
            <p class="text-sm text-gray-500">© Copyright 2024. All Rights Reserved.</p>

            <div class="flex mt-3 -mx-2 sm:mt-0">
                <a href="#" class="mx-2 text-sm text-gray-500 transition-colors duration-300 hover:text-gray-500 dark:hover:text-gray-300" aria-label="Reddit"> Teams </a>

                <a href="#" class="mx-2 text-sm text-gray-500 transition-colors duration-300 hover:text-gray-500 dark:hover:text-gray-300" aria-label="Reddit"> Privacy </a>

                <a href="#" class="mx-2 text-sm text-gray-500 transition-colors duration-300 hover:text-gray-500 dark:hover:text-gray-300" aria-label="Reddit"> Cookies </a>
            </div>
        </div>
    </div>
</footer>
</template>

<script setup>
import members from '../components/members.vue'
import { ref, onMounted } from 'vue'
import gallery from '../components/gallery.vue'
import music from '../components/music.vue'

const videoRef = ref(null)
const isPlaying = ref(false) // Track play state

function toggleVideoPlayback() {
  if (videoRef.value) {
    if (isPlaying.value) {
      videoRef.value.pause()
    } else {
      videoRef.value.play()
    }
    isPlaying.value = !isPlaying.value
  }
}

function scrollToSection(sectionId) {
  const section = document.querySelector(sectionId);
  if (section) {
    window.scrollTo({
      top: section.offsetTop,
      behavior: 'smooth',
    });
  }
}

onMounted(() => {
  // Add event listeners for video playback state
  if (videoRef.value) {
    videoRef.value.addEventListener('play', () => (isPlaying.value = true))
    videoRef.value.addEventListener('pause', () => (isPlaying.value = false))
  }
})
</script>

<style>
@keyframes fade-up {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-up {
  animation: fade-up 1s ease-out;
}
</style>
