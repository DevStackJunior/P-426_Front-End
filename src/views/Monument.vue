<script>
import SiteDecor from '../components/SiteDecor.vue'
import VisitedInfo from '../components/VisitedInfo.vue'
import Footer from '../components/Footer.vue'
import SocialShare from '../components/SocialShare.vue'
import VisitedButton from '../components/VisitedButton.vue'
import VisitedPhoto from '@/components/VisitedPhoto.vue'
import MonumentInfo from '@/components/MonumentInfo.vue'

export default {
  name: 'MonumentPage',
  components: {
    SiteDecor,
    VisitedPhoto,
    MonumentInfo,
    VisitedInfo,
    Footer,
    SocialShare,
    VisitedButton,
  },
}
</script>

<template>
  <SiteDecor />
  
  <section class="monument-section">
    <div class="monument-content">
      <VisitedPhoto 
        large-src="/src/assets/img/spoo1.jpg"
        small-top-src="/src/assets/img/spoo2.png"
        small-bottom-src="/src/assets/img/s.png"
      />
      
      <MonumentInfo 
        title="Nom du Monument"
        description="Description du lieu historique. Ajoutez ici les informations importantes sur le monument, son histoire, son architecture et sa signification culturelle."
        year="2025"
        location="Ville, Pays"
        type="Monument historique"
      />
    </div>
  </section>
  
  <VisitedInfo visitedDate="30.09.2025" :show="false" />
  <VisitedButton>
    <SocialShare />
  </VisitedButton>
  <Footer />
</template>

<style scoped>
.monument-section {
  min-height: 40vh;
  display: flex;
  align-items: center;
  background-image: url('/src/assets/img/background.png');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  padding: 3rem 2rem;
}

.monument-content {
  max-width: 1400px;
  margin: 0 auto;
  width: 100%;
  display: flex;
  gap: 3rem;
  align-items: stretch;
}

.monument-content > :first-child {
  flex: 0 0 55%;
}

.monument-content > :last-child {
  flex: 1;
}

@media (max-width: 1024px) {
  .monument-content {
    flex-direction: column;
    text-align: center;
  }
  
  .monument-section {
    min-height: auto;
    padding: 2rem 1rem;
  }
}
</style>
