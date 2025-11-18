<script>
    import FlourishMap from "@/components/FlourishMap.vue";
    import SlideShow from '@/components/SlideShow/SlideShow.vue';
    export default {
      name: "HomePage",
      components: { FlourishMap, SlideShow }
    };
    import Footer from "@/components/Footer/Footer.vue";
</script>
<template>
  <div class="home">
    <SlideShow />
    <FlourishMap visualisationId="25915215"/>
  </div>
  <Footer />
</template>

<style scoped>
.home {
  max-width: 100%;
}

.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 0 #42b883aa);
}
</style>
