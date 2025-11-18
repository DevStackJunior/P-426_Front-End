<template>
  <div class="monument-info">
    <h1 class="monument-title">{{ title }}</h1>
    <p class="monument-description">{{ description }}</p>
    <div class="monument-details">
      <p v-if="year"><strong>Année:</strong> {{ year }}</p>
      <p v-if="location"><strong>Lieu:</strong> {{ location }}</p>
      <p v-if="type"><strong>Type:</strong> {{ type }}</p>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'MonumentInfo',
  props: {
    title: {
      type: String,
      default: 'Nom du Monument',
    },
    description: {
      type: String,
      default: 'Description du lieu historique.',
    },
    year: {
      type: [String, Number],
      default: '',
    },
    location: {
      type: String,
      default: '',
    },
    type: {
      type: String,
      default: '',
    },
  },
})
</script>

<style scoped>
.monument-info {
  flex: 1;
  color: #333;
}

.monument-title {
  font-size: 2.5rem;
  font-weight: 700;
  margin: 0 0 1.5rem 0;
  color: #222;
}

.monument-description {
  font-size: 1.1rem;
  line-height: 1.8;
  margin: 0 0 2rem 0;
  color: #555;
}

.monument-details {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.monument-details p {
  margin: 0;
  font-size: 1rem;
  color: #666;
}

.monument-details strong {
  color: #333;
  margin-right: 0.5rem;
}

@media (max-width: 1024px) {
  .monument-title {
    font-size: 2rem;
  }
}
</style>
