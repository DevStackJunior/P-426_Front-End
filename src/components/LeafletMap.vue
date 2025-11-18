<template>
  <div id="map" ref="mapContainer" style="height: 600px; width: 100%;"></div>
</template>

<script>
import L from "leaflet";
import "leaflet/dist/leaflet.css";

export default {
  name: "LeafletMap",
  mounted() {
    this.map = L.map(this.$refs.mapContainer).setView([20, 0], 2);

    L.tileLayer("https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png", {
      attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a>',
    }).addTo(this.map);

    // Données statiques avec 'icon' au lieu de 'logo'
    const staticSites = [
      { id: 1, name: "Pyramides de Gizeh", lat: 29.9792, lng: 31.1342, icon: "historical.svg" },
      { id: 2, name: "Taj Mahal", lat: 27.1751, lng: 78.0421, icon: "historical.svg" },
      { id: 3, name: "Grand Canyon", lat: 36.1069, lng: -112.1129, icon: "natural.svg" },
      { id: 4, name: "Petra", lat: 30.3285, lng: 35.4444, icon: "historical.svg" }
    ];

    this.addMarkers(staticSites);
  },
  methods: {
addMarkers(sites) {
  sites.forEach(site => {
    const icon = L.icon({
      iconUrl: `/icons/${site.icon || "default.svg"}`,
      iconSize: [40, 40],
      iconAnchor: [16, 32],
      popupAnchor: [0, -32],
      className: 'marker-with-shadow'
    });

    L.marker([site.lat, site.lng], { icon })
      .addTo(this.map)
      .bindPopup(`<b>${site.name}</b>`);
  });
}
  }
};
</script>

<style scoped>
.marker-with-shadow {
  filter: drop-shadow(0 0 3px black);
}

</style>