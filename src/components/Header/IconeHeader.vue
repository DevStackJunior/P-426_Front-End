<template>
  <component
    :is="link ? 'a' : 'span'"
    :href="link || null"
    class="header-icon"
    @click="$emit('click', $event)"
  >
    <img :src="src" :alt="alt" />
  </component>
</template>

<script setup lang="ts">
defineProps<{
  src: string
  alt: string
  link?: string | null   // devient optionnel
  size?: number
}>()
defineEmits(["click"])
</script>

<style scoped>
.header-icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  margin: 0 0.5rem;
}

.header-icon img {
  width: var(--icon-size, 3rem);
  height: var(--icon-size, 3rem);
  object-fit: contain;
  transition: transform 0.6s;
}

.header-icon:hover img { 
  transform: scale(1.3);
}
</style>
