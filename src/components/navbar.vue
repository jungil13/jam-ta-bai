<template>
  <div :class="{ 'dark': isDarkMode }">
    <nav class="fixed top-0 left-0 w-full bg-white dark:bg-gray-800 shadow-md p-4 z-50">
      <div class="flex items-center justify-between">
        <!-- Logo Section -->
        <div class="flex items-center space-x-2">
          <img src="../assets/img/jtb.png" alt="logo" class="w-20 h-10">
          <span class="text-xl font-bold">𝓙𝓪𝓶 𝓽𝓪 𝓑𝓪𝓲!</span>
        </div>

        <!-- Navigation Links (Desktop) -->
        <div class="hidden md:flex space-x-6 font-semibold gap-8">
          <a href="#home" @click.prevent="scrollToSection('#home')" class="hover:text-blue-500"><i class="fas fa-solid fa-house"></i></a>
          <a href="#member" @click.prevent="scrollToSection('#member')" class="hover:text-blue-500"><i class="fas fa-solid fa-user-group"></i></a>
          <a href="#gallery" @click.prevent="scrollToSection('#gallery')" class="hover:text-blue-500"><i class="fas fa-solid fa-images"></i></a>
          <a href="#music" @click.prevent="scrollToSection('#music')" class="hover:text-blue-500"><i class="fas fa-solid fa-music"></i></a>
          <a href="#about" @click.prevent="scrollToSection('#about')" class="hover:text-blue-500"><i class="fas fa-solid fa-address-card"></i></a>
        </div>

        <!-- Drawer Toggle Button -->
        <div class="flex items-center space-x-4">
          <button @click="toggleDrawer" class="md:hidden p-2 rounded-md text-gray-900 dark:text-white hover:bg-gray-200 dark:hover:bg-gray-700 transition">
            <i class="fas fa-solid fa-bars"></i>
          </button>
          <div class="p-1">
            <button @click="openModal" class="flex items-center justify-center gap-2 font-semibold font-serif p-2 rounded-full text-black hover:text-blue-600 transition">
              <i class="fas fa-right-to-bracket text-xl"></i>
              <span class="text-lg">Login</span>
            </button>
          </div>
        </div>
      </div>
    </nav>

    <!-- Modal for Login -->
    <div v-if="showModal" class="fixed inset-0 flex items-center justify-center bg-black bg-opacity-50 z-50">
      <div class="bg-white rounded-lg shadow-lg p-8 max-w-lg mx-auto"> <!-- Adjusted padding and width -->
        <h2 class="text-2xl font-bold mb-4">Login</h2>
        <form @submit.prevent="handleLogin">
          <div class="mb-4">
            <label for="username" class="block text-sm font-medium text-gray-700">Username</label>
            <input type="text" id="username" v-model="username" class="mt-1 block w-full border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500" required>
          </div>
          <div class="mb-4">
            <label for="password" class="block text-sm font-medium text-gray-700">Password</label>
            <input type="password" id="password" v-model="password" class="mt-1 block w-full border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500" required>
          </div>
          <button type="submit" class="w-full bg-blue-600 text-white font-semibold py-2 rounded-md hover:bg-blue-700 transition">Login</button>
        </form>
        <button @click="closeModal" class="mt-4 text-blue-600 hover:underline">Cancel</button>
        <div v-if="showMessage" class="mt-4 text-center text-xl text-green-600">{{ message }}</div> <!-- Message after login -->
      </div>
    </div>

    <!-- Drawer Menu -->
    <div class="fixed top-10 left-0 w-64 h-full bg-gray-800 text-white transform transition-transform duration-300" :class="{ '-translate-x-full': !isDrawerOpen }">
      <div class="p-4">
        <h2 class="text-2xl font-bold">Menu</h2>
        <ul class="mt-4 space-y-12">
          <li><a href="#home" @click.prevent="scrollToSection('#home'); toggleDrawer()" class="hover:text-blue-400">𝐻𝑜𝓂𝑒</a></li>
          <li><a href="#member" @click.prevent="scrollToSection('#member'); toggleDrawer()" class="hover:text-blue-400">𝑀𝑒𝓂𝒷𝑒𝓇𝓈</a></li>
          <li><a href="#gallery" @click.prevent="scrollToSection('#gallery'); toggleDrawer()" class="hover:text-blue-400">𝒢𝒶𝓁𝓁𝑒𝓇𝓎</a></li>
          <li><a href="#music" @click.prevent="scrollToSection('#music'); toggleDrawer()" class="hover:text-blue-400">𝑀𝓊𝓈𝒾𝒸</a></li>
          <li><a href="#about" @click.prevent="scrollToSection('#about'); toggleDrawer()" class="hover:text-blue-400">𝒜𝒷𝑜𝓊𝓉 𝓊𝓈</a></li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const isDarkMode = ref(false);
const showModal = ref(false);
const username = ref('');
const password = ref('');
const showMessage = ref(false); // State to control message visibility
const message = ref(''); // Variable to store the message

function scrollToSection(sectionId) {
  const section = document.getElementById(sectionId.slice(1));
  if (section) {
    window.scrollTo({
      top: section.offsetTop,
      behavior: 'smooth',
    });
  }
}

const videoRef = ref(null);
const isDrawerOpen = ref(false);

function toggleDrawer() {
  isDrawerOpen.value = !isDrawerOpen.value;
}

function openModal() {
  showModal.value = true;
  showMessage.value = false; // Reset message visibility when opening modal
}

function closeModal() {
  showModal.value = false;
}

function handleLogin() {
  // Show the love message when logging in
  message.value = "I love you 😘💖😍, laag ta na hahahah"; 
  showMessage.value = true; // Show the message
  // Optionally close the modal after a delay
  setTimeout(() => {
    closeModal(); // Close modal after 3 seconds
  }, 10000);
}

onMounted(() => {
  if (videoRef.value) {
    videoRef.value.play();
  }
});
</script>

<style scoped>
/* Add any additional styles for your modal or other elements here */
</style>
