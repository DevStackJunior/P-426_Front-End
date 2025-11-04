<script setup lang="ts">
import Header from './components/Header/Header.vue'
</script>

<template>
  <Header></Header>
  <footer>@unesco</footer>
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
  filter: drop-shadow(0 0 0 #42b883aa);
}
footer {
  background-color: #914435;
  color: white;
  text-align: center;
  padding: 1rem 0;
  font-size: 1.1rem;
  width: 100%;
  position: fixed;
  bottom: 0;
  left: 0;
}
</style>
