<script setup lang="ts">
import  { ref } from 'vue'
import LoginForm from '../components/LoginForm.vue'
const formSended = ref(false)
</script>

<template>
  <main>
    <LoginForm @loginEnd="formSended = true"> </LoginForm>
    <div v-if="formSended">
      Il form è stato inviato correttamente
    </div>
  </main>
</template>
