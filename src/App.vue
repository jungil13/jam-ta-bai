<script setup>
import { RouterLink, RouterView } from 'vue-router'
import navbar from './components/navbar.vue'
</script>
<template>
  <header>
    <navbar/>
  </header>
  <RouterView />
</template>
