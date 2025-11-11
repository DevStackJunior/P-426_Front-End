<script>
import SiteDecor from '../components/SiteDecor.vue'
import VisitedInfo from '../components/VisitedInfo.vue'
import Footer from '../components/Footer.vue'
import SocialShare from '../components/SocialShare.vue'
import Background from '../components/Background.vue'
import VisitedButton from '../components/VisitedButton.vue'
import VisitedPhoto from '@/components/VisitedPhoto.vue'

export default {
  name: 'MonumentPage',
  components: {
    SiteDecor,
    VisitedInfo,
    Footer,
    SocialShare,
    VisitedButton,
    Background,
    VisitedPhoto,
  },
}
</script>

<template>
  <SiteDecor />
  <!-- <VisitedPhoto /> -->
  <VisitedInfo visitedDate="30.09.2025" :show="true" />
  <SocialShare />
  <!-- <VisitedButton /> -->
  <Background />
  <Footer />
</template>
