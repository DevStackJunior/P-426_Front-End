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

  position: fixed; 
  top: 160px;      
  right: 40px;        
  bottom: 0;    
  z-index: 900;    
}
</style>
