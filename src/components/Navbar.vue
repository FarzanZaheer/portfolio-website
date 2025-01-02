<template>

  <div class="flex justify-end items-center">
    <div class="grow"><span class="primary-50">Farzan </span><span class="secondary-50">Zaheer</span></div>
    <Button as="router-link" rounded label="Home" to="/"></Button>
    <Button as="router-link" class="ml-2" rounded label="Resume" to="/resume"></Button>
    <Button as="router-link" class="ml-2" rounded label="Contact" to="/contact"></Button>
  </div>

</template>

<script setup>

  import Button from "primevue/button"

</script>