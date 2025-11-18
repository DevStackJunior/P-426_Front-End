<script setup lang="ts">
import { ref } from 'vue'
import Icone from './IconeHeader.vue'
import UnescoIcon from './IconeUnesco.vue'
import Pop_up from '@/components/Pop_up/Pop_up_connection.vue'

import mapIcon from '../../assets/maps.png'
import staticticsIcon from '../../assets/statistics.png'
import userIcon from '../../assets/user.png'
import UNESCO from '../../assets/UNESCO-Simbolo.png'

// Etat du pop-up
const isLoginOpen = ref(false)

// Ouvrir le pop-up
const openLoginPopup = () => {
  isLoginOpen.value = true
}

// Fermer le pop-up
const closeLoginPopup = () => {
  isLoginOpen.value = false
}
</script>

<template>
  <header class="header">
    <UnescoIcon :src="UNESCO" alt="Unesco" link="/" />

    <nav class="nav">
      <router-link to="/map"><Icone :src="mapIcon" alt="Map" link="/" /></router-link>
      <router-link to="/stats"><Icone :src="staticticsIcon" alt="Stats" link="#" /></router-link>

      <!-- Icône utilisateur -->
      <span @click="openLoginPopup">
        <Icone :src="userIcon" alt="User"/>
      </span>
    </nav>

    <!-- Pop-up connexion -->
    <Pop_up 
      :isOpen="isLoginOpen"
      @close="closeLoginPopup" 
    />
  </header>
</template>


<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: #FFB1A2;
  color: white;
  padding: 1rem 2rem;
  border-bottom: 16px solid #B73F28;
}

.nav a,
.nav span {
  color: white;
  text-decoration: none;
  margin-left: 3rem;
  cursor: pointer;
}

.nav a:hover,
.nav span:hover {
  text-decoration: underline;
}
</style>
