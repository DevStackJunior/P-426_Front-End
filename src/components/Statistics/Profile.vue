<template>
  <section class="Profile-card">
    <img
      src="@/assets/user.png"
      alt="Profile picture"
      class="profile-pic"
    />
    <div class="info">
      <p><strong>Pays:</strong> Suisse</p>
      <p><strong>Ville:</strong> Lausanne</p>
      <p><strong>Bio:</strong> J'adore voyager</p>
    </div>
  </section>
</template>

<script setup lang="ts">

</script>

<style scoped>
.Profile-card {
  position: absolute;
  top: 150px;
  left: 20px;  
  background-color: #FB816A;
  border-radius: 20px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
  width: 260px;
  padding: 1.5rem;
  text-align: left;
  color: white;
  font-family: 'Arial', sans-serif;
}

.profile-pic {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  object-fit: cover;
  margin-bottom: 1rem;
}

.info p {
  margin: 0.4rem 0;
  font-size: 1rem;
}
</style>
