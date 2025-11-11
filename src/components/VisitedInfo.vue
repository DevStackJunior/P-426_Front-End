<script setup lang="ts">
defineProps<{
  visitedDate: string
  show?: boolean
}>()
</script>

<template>
  <div v-if="show" class="visited-container-wrapper">
    <div class="visited-container">
      <div class="visited-left">
        <div class="visited-header">
          <h2 class="visited-title">Visité</h2>
        </div>
        <p class="visited-date">{{ visitedDate }}</p>
      </div>

      <div class="visited-right">
        <img
          src="../assets/img/visited-check.png"
          alt="Icône de vérification"
          class="visited-icon"
        />
      </div>
    </div>
  </div>

  <!-- Bloc partage (affiché seulement si showShare est true) -->
  <div v-if="show" class="share-block">
    <p>Voulez-vous le partager avec vos amis ?</p>
  </div>
</template>

<style scoped>
.visited-container-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: flex-end; /* pousse le contenu en bas */
  min-height: 60vh; /* prend toute la hauteur de la page */
}
.visited-container {
  display: flex;
  gap: 1rem;
  font-family: 'Poppins', sans-serif;
  justify-content: center;
  align-items: stretch;
}
.visited-left {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.visited-title {
  font-size: 1.4rem;
  font-weight: 600;
  margin: 0;
}

.visited-date {
  font-size: 1.2rem;
  font-weight: 500;
  color: #4b4b4b;
}

.visited-right {
  display: flex;
  align-items: center;
  justify-content: center;
}

.visited-icon {
  width: 90px; /* ajuste selon ton besoin */
  height: 100%;
  object-fit: contain; /* pour que l'image garde ses proportions */
}

.share-block {
  text-align: center;
  font-weight: 400;
}
</style>
