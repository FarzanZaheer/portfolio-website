
<template>

    <!-- <div class="wrapper"> -->
      <Navbar />
    <!-- </div> -->

  <RouterView />
</template>

<script setup lang="ts">
  import { RouterLink, RouterView } from 'vue-router'
  import Navbar from './components/Navbar.vue';
</script>

<style scoped>
</style>
