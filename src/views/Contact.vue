<template>
  <div class="contact-form">
    <div class="g-recaptcha" data-sitekey="6Ld0qrAqAAAAAK1WBfXYMN1f2JM-drjKBInGxJBu"></div> <!-- replace with your recaptcha SITE key not secret key -->
    <div>Contact</div>
    <div class="my-4">
      <div>Full Name</div>
      <InputText size="large" class="grow" type="text" name="name" v-model="name"/>
    </div>
    <div class="my-4">
      <div>Email</div>
      <InputText size="large" class="grow" type="email" name="email"  v-model="email"/>
    </div>
    <div class="my-4">
      <div>Message</div>
      <Textarea size="large" class="grow" v-model="message" rows="5" cols="30" />
    </div>
    <div class="my-4">
      <Button @click="submitForm">Send Message</Button>
    </div>
  </div>
</template>

<script setup>
  import {ref} from 'vue'
  import InputText from 'primevue/inputtext'
  import Button from 'primevue/button'
  import Textarea from 'primevue/textarea'

  const name = ref('')
  const email = ref('')
  const message = ref('')

  const submitForm = async () => {
    const response = await fetch("https://formspree.io/f/xnnnoonl", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
        Accept: "application/json",
      },
      body: JSON.stringify({
        name: name.value,
        email: email.value,
        message: message.value,
      }),
    });
    const result = await response.json()
    console.log('res', result)
    if (result.success) {
      console.log(result)
    }
  }
</script>