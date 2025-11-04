<template>
  <a :href="link" target="_blank" class="header-icon">
    <img :src="src" :alt="alt" />
  </a>
</template>

<script setup lang="ts">
defineProps<{
  src: string
  alt: string
  link: string
  size?: number // taille optionnelle
}>()
</script>

<style scoped>
.header-icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  margin: 0 0.5rem;
}

.header-icon img {
  max-width: 100%;
  max-height: 100%;
  object-fit: contain;
  transition: transform 0.6s;
}

/* tu peux définir une taille par défaut */
.header-icon img {
  width: var(--icon-size, 3rem);
  height: var(--icon-size, 3rem);
}

.header-icon:hover img { 
    transform: scale(1.3);       /* agrandir */
    /*filter: drop-shadow(1em 0 0 #42b883aa);*/
}
</style>
