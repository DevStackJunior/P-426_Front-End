
<script setup lang="ts">
import Icone from './Icone.vue';
import mapIcon from '../../assets/maps.png'
import staticticsIcon from '../../assets/statistics.png'
import  userIcon from '../../assets/user.png'
import  UNESCO from '../../assets/UNESCO-Simbolo.png'
import UnescoIcon from './UnescoIcon.vue';
</script>

<template>
  <header class="header">
    <UnescoIcon :src="UNESCO" alt="Unesco" link="#"/>
    <nav class="nav">
      <Icone :src="mapIcon" alt="Map" link="#"/>
      <Icone :src="staticticsIcon" alt="Stats" link="#"/>
      <Icone :src="userIcon" alt="User" link="#"/>
    </nav>
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

.logo {
  font-size: 1.5rem;
}

.nav a {
  color: white;
  text-decoration: none;
  margin-left: 3rem;
}

.nav a:hover {
  text-decoration: underline;
}
</style>
