<script setup lang="ts">
defineProps<{
  showShare?: boolean
}>()
</script>

<template>
  <div class="visited-container-wrapper">
    <button class="visited-button">Avez-vous vsisité ce lieu ?</button>

    <div class="share-block">
      <p>Voulez-vous le partager avec vos amis ?</p>
      <slot></slot>
    </div>
  </div>
</template>

<style scoped>
.visited-container-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  min-height: 60vh;
  align-items: center;
}

.visited-button {
  font-family: 'Poppins', sans-serif;
  font-size: 1.2rem;
  font-weight: 500;
  padding: 1rem 2rem;
  background-color: #4caf50;
  color: white;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.visited-button:hover {
  background-color: #45a049;
}

.visited-button:active {
  transform: scale(0.98);
}

.share-block {
  text-align: center;
  font-weight: 400;
  margin-top: 1.5rem;
}
</style>
