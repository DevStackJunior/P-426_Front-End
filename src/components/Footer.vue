<template>
  <footer class="app-footer">© - UNESCO</footer>
</template>

<script setup>
// Pas de logique nécessaire
</script>

<style scoped>
.app-footer {
  position: fixed; /* reste toujours visible */
  bottom: 0; /* collé en bas */
  left: 0;
  width: 100%; /* prend toute la largeur */
  background-color: #a0352d; /* brun chaud / brick */
  color: #fff;
  text-align: center;
  padding: 1rem 0;
  font-weight: 500;
  letter-spacing: 0.5px;
  z-index: 1000; /* reste au-dessus du contenu */
}
</style>
