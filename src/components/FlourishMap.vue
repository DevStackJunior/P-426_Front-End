<template>
  <div ref="container" class="flourish-wrapper"></div>
</template>

<script>
export default {
  name: "FlourishMap",
  mounted() {
    const container = this.$refs.container;

    // Crée le div avec l'attribut data-src
    const embedDiv = document.createElement("div");
    embedDiv.className = "flourish-embed flourish-map";
    embedDiv.setAttribute("data-src", "visualisation/25887981");
    embedDiv.style.width = "100%";    // largeur
    embedDiv.style.height = "900px";  // hauteur
    container.appendChild(embedDiv);

    // Vérifie si le script Flourish est déjà chargé
    const scriptUrl = "https://public.flourish.studio/resources/embed.js";
    if (!document.querySelector(`script[src="${scriptUrl}"]`)) {
      const script = document.createElement("script");
      script.src = scriptUrl;
      script.async = true;
      document.body.appendChild(script);
    } else if (window.Flourish?.Live) {
      window.Flourish.Live.init(); // force l'initialisation si script déjà chargé
    }
  }
};
</script>
