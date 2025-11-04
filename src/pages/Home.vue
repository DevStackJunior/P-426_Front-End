<template>
  <div class="home">
    <!-- Render the Flourish map HTML -->
    <div v-html="flourishEmbed"></div>
  </div>
</template>

<script>
export default {
  name: "HomePage",
  data() {
    return {
      flourishEmbed: `
        <div class="flourish-embed flourish-map" data-src="visualisation/25915215">
          <noscript>
            <img src="https://public.flourish.studio/visualisation/25915215/thumbnail" width="100%" alt="map visualization" />
          </noscript>
        </div>
      `
    };
  },
  mounted() {
    // Check if the Flourish script is already loaded
    if (!document.querySelector('script[src="https://public.flourish.studio/resources/embed.js"]')) {
      const script = document.createElement("script");
      script.src = "https://public.flourish.studio/resources/embed.js";
      script.async = true;
      document.body.appendChild(script);
    }
  }
};
</script>

<style scoped>
.home {
  max-width: 100%;
}
</style>
