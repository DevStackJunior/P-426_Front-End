<script setup lang="ts">
import { ref } from 'vue'

defineProps<{
  showShare?: boolean
}>()

const showCalendar = ref(false)
const selectedDate = ref('')

const handleButtonClick = () => {
  showCalendar.value = true
}

const handleDateSelect = (event: Event) => {
  const target = event.target as HTMLInputElement
  selectedDate.value = target.value
  // Vous pouvez émettre un événement ici si nécessaire
}
</script>

<template>
  <div class="visited-container-wrapper">
    <button v-if="!showCalendar" class="visited-button" @click="handleButtonClick">
      Avez-vous vsisité ce lieu ?
    </button>

    <div v-if="showCalendar" class="calendar-container">
      <p class="calendar-label">Sélectionnez la date de votre visite :</p>
      <input
        type="date"
        v-model="selectedDate"
        @change="handleDateSelect"
        class="date-picker"
        :max="new Date().toISOString().split('T')[0]"
      />
      <p v-if="selectedDate" class="selected-date-text">
        Date sélectionnée : {{ new Date(selectedDate).toLocaleDateString('fr-FR') }}
      </p>
    </div>

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
  min-height: 23vh;
  align-items: center;
}

.visited-button {
  font-family: 'Poppins', sans-serif;
  font-size: 1.2rem;
  font-weight: 500;
  padding: 0.2rem 0.5rem;
  background-color: #4caf50;
  color: white;
  border: none;
  border-radius: 32px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.visited-button:hover {
  background-color: #45a049;
}

.visited-button:active {
  transform: scale(0.98);
}

.calendar-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
  padding: 1.5rem;
  background-color: rgba(255, 255, 255, 0.95);
  border-radius: 12px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.calendar-label {
  font-family: 'Poppins', sans-serif;
  font-size: 1.1rem;
  font-weight: 500;
  color: #333;
  margin: 0;
}

.date-picker {
  font-family: 'Poppins', sans-serif;
  font-size: 1rem;
  padding: 0.75rem 1rem;
  border: 2px solid #4caf50;
  border-radius: 8px;
  cursor: pointer;
  transition: border-color 0.3s ease;
  min-width: 200px;
}

.date-picker:hover {
  border-color: #45a049;
}

.date-picker:focus {
  outline: none;
  border-color: #45a049;
  box-shadow: 0 0 0 3px rgba(76, 175, 80, 0.2);
}

.selected-date-text {
  font-family: 'Poppins', sans-serif;
  font-size: 0.95rem;
  color: #4caf50;
  font-weight: 500;
  margin: 0;
}

.share-block {
  text-align: center;
  font-weight: 400;
  margin-top: 1.5rem;
}
</style>
