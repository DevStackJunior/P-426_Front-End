<template>
  <aside class="sidebar">
    <!-- Tu pourras plus tard y insérer des composants enfants ou du texte -->
    <slot />
  </aside>
</template>

<script setup lang="ts">
// pas besoin de props pour l'instant
</script>

<style scoped>
.sidebar {
  width: 280px;              /* largeur fixe */
  background-color: #E13319; /* ton rouge foncé UNESCO */
  border-radius: 20px 20px 0 0;
  padding: 1.5rem;
  color: white;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;

  position: fixed; /* ✅ reste collée au bord */
  top: 160px;      /* adapte à la hauteur du header */
  right: 40px;        /* ✅ colle complètement au bord droit */
  bottom: 0;    /* laisse un peu d’espace pour le footer */
  z-index: 900;    /* reste au-dessus de la carte si besoin */
}
</style>
