<template>
  <!-- Overlay sombre -->
  <div v-if="isOpen" class="overlay" @click.self="emit('close')">
    
    <!-- Pop-up centré -->
    <div class="login-popup">
      <form @submit.prevent="handleLogin">
        <h3>Connexion</h3>

        <label for="username">Username :</label>
        <input id="username" v-model="username" type="username" required />

        <label for="password">Mot de passe :</label>
        <input id="password" v-model="password" type="password" required />

        <button type="submit" formmethod="post">Se connecter</button>
      </form>
      <span>Vous n'avez pas de compte ? <a href="/page-register">Créer un compte</a></span>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, defineProps, defineEmits } from 'vue'

const props = defineProps<{ isOpen: boolean }>()
const emit = defineEmits<{ (event: 'close'): void }>()

const username = ref('')
const password = ref('')

const handleLogin = async () => {
  try {
    const res = await fetch('http://localhost:3333/user/login', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({
        username: username.value,
        password: password.value
      })
    })

    const data = await res.json()

    if (!res.ok) {
      alert(data.error || 'Erreur lors de la connexion')
      return
    }

    // Stocker le token (localStorage ou Pinia)
    localStorage.setItem('token', data.token.token)

    console.log('Connexion réussie :', data)
    emit('close')

  } catch (err) {
    console.error(err)
    alert('Impossible de contacter le serveur')
  }
}

</script>

<style scoped>
/*******************
 * OVERLAY (fond)
 *******************/
.overlay {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.45);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 999;
  animation: fadeIn 0.25s ease;
}
/*******************
 * POP-UP
 *******************/
.login-popup {
  background: white;
  padding: 1.8rem;
  border-radius: 10px;
  min-width: 320px;
  box-shadow: 0 5px 20px rgba(0,0,0,0.25);
  animation: popIn 0.25s ease;
}
.login-popup label {
  font-size: 0.95rem;
  font-weight: 500;
  color: #111;
}
.login-popup h3 {
  font-weight: 900;
  color: #111;
  text-align: center;
}
.login-popup form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
.login-popup span {
  font-size: 0.95rem;
  font-weight: 500;
  color: #111;
}
.login-popup a {
  font-size: 0.95rem;
  font-weight: 500;
  color: #B73F28;
}

.login-popup input {
  box-sizing: border-box;
  width: 100%;
  background: #fff;
  border: 1px solid #ccc !important;
  border-radius: 6px;
  padding: 0.55rem 0.7rem;
  font-size: 0.9rem;
  color: #111;
}

.login-popup input:focus {
  border-color: #B73F28 !important;
  outline: none;
  box-shadow: 0 0 0 2px rgba(235, 94, 0, 0.25);
}

.login-popup button[type='submit'] {
  width: 100%;
  background-color: #B73F28;
  color: white;
  padding: 0.65rem;
  border-radius: 6px;
  cursor: pointer;
  border: none;
  font-size: 1rem;
  transition: 0.2s;
}

.login-popup button:hover {
  background-color: #d84a2e;
}

/*******************
 * Animations
 *******************/
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes popIn {
  from { transform: scale(0.85); opacity: 0; }
  to { transform: scale(1); opacity: 1; }
}
</style>
