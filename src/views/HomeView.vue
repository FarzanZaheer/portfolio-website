<template>

  <div class="flex">
    <div>
      <small>Fullstack Developer</small>
      <div>Farzan Zaheer</div>
      <p>Hello, I am a full stack developer with 6+ years of experience</p>
      <Socials />
    </div>

    <Image :src="photo" alt="Image" width="250" />
  </div>

</template>

<script setup>
  import photo from '@/assets/photo1.jpg'
  import Image from "primevue/image"

  import Socials from '@/components/Socials.vue'

</script>