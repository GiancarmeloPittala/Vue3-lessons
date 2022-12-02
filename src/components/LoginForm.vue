<template>
  <div class=" my-10 grid gap-4">
    <input v-model="user.nickname" type="text" name="text" id="text">
    <input v-model="user.email" type="email" name="email" id="email">
    <input v-model="user.password" type="password" name="password" id="password">
    <button class="border-green-900 border-2" @click="login()"> Login </button>
    <div>
      <slot name="slot1"></slot>
    </div>
    <div v-html="messaggio" v-if="showMessage" ></div>
  </div>
</template>

<style>
input {
  padding: .2rem;
  border: 2px solid black;
  border-radius: 20px;
}
</style>

<script setup lang="ts">
import { ref, reactive, computed, watch } from 'vue';
const emit = defineEmits(['loginEnd'])
const showMessage = ref(false)
const messaggio = ref("messaggio di prova");
const user = reactive({
  nickname: '',
  email: '',
  password: ''
})

const nome_completo = computed(() => {
  return user.nickname + " " + user.email
})

// methods 
function login() {
  showMessage.value = true

  setTimeout(() => {
    showMessage.value = false
  }, 2000)

  if (user.nickname.length < 2) {
    messaggio.value += `Nickname almeno 2 caratteri <br/>`
  }
  if (user.email.length < 2) {
    messaggio.value += `email non valida`
  }

  // solleviamo un emit
  emit('loginEnd')
}

watch( user, (newValue,oldValue) => {
  console.log( newValue, oldValue )
  // ...

} )


</script>