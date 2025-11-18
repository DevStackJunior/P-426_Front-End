<template>
  <div class="home">
    <!-- Leaflet map component -->
    <LeafletMap :sites="staticSites" />
  </div>
</template>

<script>
import LeafletMap from "@/components/LeafletMap.vue";

export default {
  name: "HomePage",
  components: { LeafletMap },
  data() {
    return {
      // Static demo data for the map
      staticSites: [
        { id: 1, name: "Pyramides de Gizeh", lat: 29.9792, lng: 31.1342, icon: "historical.svg" },
        { id: 2, name: "Taj Mahal", lat: 27.1751, lng: 78.0421, icon: "historical.svg" },
        { id: 3, name: "Grand Canyon", lat: 36.1069, lng: -112.1129, icon: "natural.svg" },
        { id: 4, name: "Petra", lat: 30.3285, lng: 35.4444, icon: "historical.svg" }
      ]
    };
  }
};
</script>

<style scoped>
.home {
  max-width: 100%;
}
</style>
