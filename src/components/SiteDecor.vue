<script setup></script>

<template>
  <div class="decor">
    <img
      src="../assets/img/left-corner-img.png"
      class="deco-left"
      alt="Décoration gauche"
    />
    <img
      src="../assets/img/right-corner-img.png"
      class="deco-right"
      alt="Décoration droite"
    />
  </div>
</template>

<style scoped>
.decor {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: 0;
}

.deco-left,
.deco-right {
  position: absolute;
  bottom: 0;
  opacity: 0.25;
  width: 460px;
}

.deco-left {
  left: 0;
}

.deco-right {
  right: 0;
}
</style>
