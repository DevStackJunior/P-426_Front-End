<template>
  <div
    class="background-band"
    :style="{
      backgroundImage: '../assets/img/background.png',
      top: position + 'px',
      height: height,
    }"
  ></div>
</template>

<script>
export default {
  name: 'Background',
  props: {
    position: {
      type: Number,
      default: 0, // position verticale en pixels
    },
    height: {
      type: String,
      default: '200px', // hauteur de la bande
    },
  },
}
</script>

<style scoped>
.background-band {
  position: absolute; /* pour positionner verticalement sur la page */
  width: 100%;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}
</style>
