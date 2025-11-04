<template>
  <a :href="link" target="_blank" class="header-icon-large">
    <img :src="src" :alt="alt" />
  </a>
</template>

<script setup lang="ts">
defineProps<{
  src: string
  alt: string
  link: string
}>()
</script>

<style scoped>
.header-icon-large img {
  width: 100%;  /* plus grand que les autres icônes */
  height: 4rem;
  object-fit: contain;
}
</style>
