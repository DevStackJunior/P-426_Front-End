<script setup lang="ts">
import { ref, onMounted } from 'vue'
import axios from 'axios'
import SlideShow from './SlideShow.vue'

const sitesVisites = ref([])
const sitesAVisiter = ref([])

// exemple d'URL de ton API AdonisJS
const API_BASE = 'http://localhost:3333/api'

// récupération des données au montage
onMounted(async () => {
  try {
    const [visitesRes, aVisiterRes] = await Promise.all([
      axios.get(`${API_BASE}/`),
      axios.get(`${API_BASE}/users/:user_id/visits?limit=:limit`)
    ])
    sitesVisites.value = visitesRes.data
    sitesAVisiter.value = aVisiterRes.data
  } catch (error) {
    console.error('Erreur lors du chargement des sites', error)
  }
})
</script>

<template>
  <SlideShow>
    <section>
      <h2>A découvrir</h2>
      <ul>
        <li v-for="site in sitesAVisiter" :key="site.id">
          <img src="/icons/unesco-icon.svg" alt="" width="20" />
          {{ site.nom }}
        </li>
      </ul>
    </section>

    <hr />

    <section>
      <h2>Sites visités</h2>
      <ul>
        <li v-for="site in sitesVisites" :key="site.id">
          <img src="/icons/unesco-icon.svg" alt="" width="20" />
          {{ site.nom }}
        </li>
      </ul>
    </section>
</SlideShow>
</template>

<style scoped>
h2 {
  color: white;
  font-size: 1.2rem;
  margin-bottom: 0.5rem;
}
ul {
  list-style: none;
  padding: 0;
  margin: 0 0 1rem 0;
}
li {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-bottom: 0.5rem;
}
hr {
  border: none;
  border-top: 1px solid rgba(255, 255, 255, 0.4);
  margin: 1rem 0;
}
</style>
