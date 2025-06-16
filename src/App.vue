<script setup>
import HelloWorld from './components/HelloWorld.vue'
import ConditionalRendering from './components/ConditionalRendering.vue'
import DataAss from "./components/DataAss.vue"
</script>

<template>
  <HelloWorld msg="Vite + Vue" />
  <ConditionalRendering />
  <DataAss />
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
