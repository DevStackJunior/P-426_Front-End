<template>
  <div class="visited-photo">
    <div class="photos" role="group" aria-label="Photos">
      <img v-if="largeSrc" class="large" :src="largeSrc" :alt="largeAlt" loading="lazy" />

      <div class="small-stack">
        <img v-if="smallTopSrc" class="small top" :src="smallTopSrc" :alt="smallTopAlt" loading="lazy" />
        <img v-if="smallBottomSrc" class="small bottom" :src="smallBottomSrc" :alt="smallBottomAlt" loading="lazy" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'VisitedPhoto',
  props: {
    largeSrc: {
      type: String,
      default: '',
    },
    smallTopSrc: {
      type: String,
      default: '',
    },
    smallBottomSrc: {
      type: String,
      default: '',
    },
    largeAlt: {
      type: String,
      default: 'Grande photo',
    },
    smallTopAlt: {
      type: String,
      default: 'Petite photo haut',
    },
    smallBottomAlt: {
      type: String,
      default: 'Petite photo bas',
    },
    title: {
      type: String,
      default: '',
    },
    content: {
      type: String,
      default: '',
    },
  },
})
</script>

<style scoped>
.visited-photo {
  display: flex;
  width: 100%;
  height: 100%;
  justify-content: space-between;
}

.photos {
  display: flex;
  gap: 1.5rem;
  align-items: center;
  width: 100%;
  justify-content: center;
}

.photos img {
  display: block;
  object-fit: contain;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.large {
  width: 300px;
  height: 400px;
  flex-shrink: 0;
}

.small-stack {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.small {
  width: 180px;
  height: 195px;
  flex-shrink: 0;
}

/* Responsive: stack vertically on narrow screens */
@media (max-width: 800px) {
  .visited-photo {
    flex-direction: column;
  }

  .photos {
    width: 100%;
    justify-content: center;
    gap: 1rem;
  }

  .large {
    width: 180px;
    height: 180px;
  }

  .small {
    width: 120px;
    height: 80px;
  }
}
</style>
