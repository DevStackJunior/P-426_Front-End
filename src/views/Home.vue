<script>
import FlourishMap from '@/components/FlourishMap.vue'

export default {
  name: 'HomePage',
  components: { FlourishMap },
}
</script>

<template>
  <div class="home">
    <FlourishMap visualisationId="25915215" />
  </div>
</template>

<style scoped>
.home {
  max-width: 100%;
}
</style>
