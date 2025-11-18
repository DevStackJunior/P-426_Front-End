<template>
  <div class="social-links">
    <a href="https://instagram.com" target="_blank" rel="noopener">
      <img src="../assets/icons/instagram.png" class="logo" alt="instagram logo" />
    </a>
    <a href="https://twitter.com" target="_blank" rel="noopener">
      <img src="../assets/icons/twitter.png" class="logo" alt="X logo" />
    </a>
    <a href="https://facebook.com" target="_blank" rel="noopener">
      <img src="../assets/icons/facebook.png" class="logo" alt="Facebook logo" />
    </a>
  </div>
</template>

<script>
export default {
  name: 'SocialLinks',
}
</script>

<style scoped>
.social-links {
  display: flex;
  gap: 60px;
  /* margin-top: 40px; pushes the icons down */
  justify-content: center;
  /* font-size is not needed for images, you control size via width/height */
}

.social-links a {
  display: inline-block; /* ensures width/height apply correctly */
  transition: transform 0.3s; /* optional hover effect */
}

.social-links a img {
  width: 40px; /* set the desired width */
  height: 40px; /* set the desired height */
  object-fit: contain; /* keeps aspect ratio for SVG/PNG */
  transition: transform 0.3s;
}

.social-links a:hover img {
  transform: scale(1.2); /* simple zoom effect on hover */
}
</style>
