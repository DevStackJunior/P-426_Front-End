<script setup lang="ts">
defineProps<{
  background?: string // couleur / gradient / image
  height?: string // hauteur de la bande
  position?: 'top' | 'bottom' // emplacement de la bande
}>()
</script>

<template>
  <div
    class="background-band"
    :class="[position]"
    :style="{
      '--band-bg': background || '#f3f3f3',
      '--band-height': height || '120px',
    }"
  ></div>
</template>

<style scoped>
.background-band {
  width: 100%;
  height: var(--band-height);
  background: var(--band-bg);
  background-size: cover; /* ajuste l'image à la bande */
  background-position: center; /* centre l'image */
  background-repeat: no-repeat; /* pas de répétition par défaut */
  position: absolute;
  left: 0;
  right: 0;
  z-index: 1;
}

/* Position haute */
.background-band.top {
  top: 0;
}

/* Position basse */
.background-band.bottom {
  bottom: 0;
}
</style>
