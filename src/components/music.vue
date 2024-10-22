<template>
  <section class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 p-12">
    <!-- CARD 1 -->
    <div class="bg-gray-900 rounded-lg overflow-hidden shadow-black shadow-lg transition translate scale-100 hover:scale-105">
      <img class="w-full h-48 object-cover" src="https://upload.wikimedia.org/wikipedia/en/f/f1/Tycho_-_Epoch.jpg" alt="The Coldest Sunset" />
      <div class="px-6 py-4">
        <div class="text-xl mb-2 text-white">𝒫𝒾𝓈𝓀𝑜𝓉
        </div>
        <p class="text-gray-400 text-base">
          By: Renz Kayle Ando
        </p>
      </div>
      <div class="px-6 pt-4 pb-2">
        <audio controls class="w-full mt-4">
        <source src="../assets/music/piskot.mp3" type="audio/mpeg" />
        Your browser does not support the audio element.
      </audio>
      </div>
    </div>
    <!-- END OF CARD 1 -->

    <!-- CARD 2 -->
    <div class="bg-gray-900 rounded-lg overflow-hidden shadow-black shadow-lg transition translate scale-100 hover:scale-105">
      <img class="w-full h-48 object-cover" src="https://upload.wikimedia.org/wikipedia/en/c/ca/Tycho_-_Awake.png" alt="Awake" />
      <div class="px-6 py-4">
        <div class="text-xl mb-2 text-white">𝒜𝓌𝒶𝓀𝑒</div>
        <p class="text-gray-400 text-base">By: Renz Kayle Ando</p>
      </div>
      <div class="px-6 pt-4 pb-2">
        <audio controls class="w-full mt-4">
        <source src="../assets/music/piskot.mp3" type="audio/mpeg" />
        Your browser does not support the audio element.
      </audio>
      </div>
    </div>
    <!-- END OF CARD 2 -->

    <!-- CARD 3 -->
    <div class="bg-gray-900 rounded-lg overflow-hidden shadow-black shadow-lg transition translate scale-100 hover:scale-105">
      <img class="w-full h-48 object-cover" src="https://upload.wikimedia.org/wikipedia/en/f/f1/Tycho_-_Epoch.jpg" alt="The Coldest Sunset" />
      <div class="px-6 py-4">
        <div class="text-xl mb-2 text-white">𝒯𝒽𝑒 𝒞𝑜𝓁𝒹𝑒𝓈𝓉 𝒮𝓊𝓃𝓈𝑒𝓉</div>
        <p class="text-gray-400 text-base">By: Renz Kayle Ando</p>
      </div>
      <div class="px-6 pt-4 pb-2">
        <audio controls class="w-full mt-4">
        <source src="../assets/music/piskot.mp3" type="audio/mpeg" />
        Your browser does not support the audio element.
      </audio>
      </div>
    </div>
    <!-- END OF CARD 3 -->
  </section>
</template>

<style scoped>
audio::-webkit-media-controls-panel {
  background-color: #90d2dd;
}

audio::-webkit-media-controls-time-remaining-display {
  color: #fff;
}
</style>