<template>
  <header class="flex items-center justify-between">
    <div>
      <img width="50" height="50" :src="props.logoImg" alt="logo">
    </div>
    <nav>
      <ul class="flex gap-4 items-center">
        <li v-for="item of menu">
          <router-link :to="item.href">{{ item.text }}
          </router-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script setup lang="ts">
// Data
const menu = [{
  href: '/',
  text: 'Home'
},{
  href: '/about',
  text: 'About'
}]

// Props
const props = defineProps({
  logoImg: String
})

</script>

