<script setup>
import { ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router'
import Header from './components/Header.vue'


</script>

<template>
  <Header :logoImg="'https://source.unsplash.com/random?tree'" />
  <RouterView />
</template>

<style scoped>

</style>
