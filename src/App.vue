
<template>
  <div class="app-container m-6 p-6">
    <Navbar />
    <div class="view-container m-6 p-6">
      <RouterView />
    </div>
  </div>
</template>

<script setup lang="ts">
  import { RouterLink, RouterView } from 'vue-router'
  import Navbar from './components/Navbar.vue';
</script>

<style scoped>
</style>
