<template>
  <!-- <form @submit.prevent="submitForm"> -->
    <!-- <div class=""> -->
      <div class="my-4">
        <InputText class="grow" type="text" name="name" v-model="name"/>
      </div>
      <div class="my-4">
        <InputText class="grow" type="email" name="email"  v-model="email"/>
      </div>
      <div class="my-4">
        <Textarea class="grow" v-model="message" rows="5" cols="30" />
      </div>
      <div class="my-4">
        <Button @click="submitForm">Send Message</Button>
      </div>
      
    <!-- </div> -->
    
  <!-- </form> -->
</template>

<script setup>
  import {ref} from 'vue'
  import InputText from 'primevue/inputtext'
  import Button from 'primevue/button'
  import Textarea from 'primevue/textarea'


  const WEB3FORMS_ACCESS_KEY = "de5ccc21-c7f1-4822-a2d1-6ccd0b26ea12";

  const name = ref('')
  const email = ref('')
  const message = ref('')

  const submitForm = async () => {
    const response = await fetch("https://api.web3forms.com/submit", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
        Accept: "application/json",
      },
      body: JSON.stringify({
        access_key: WEB3FORMS_ACCESS_KEY,
        name: name.value,
        email: email.value,
        message: message.value,
      }),
    });
    const result = await response.json()
    if (result.success) {
      console.log(result)
    }
  }
</script>