<template>
  <div class="visited-photo">
    <div class="photos" role="group" aria-label="Photos">
      <img class="large" src="../assets/img/s.png" :alt="largeAlt" loading="lazy" />

      <div class="small-stack">
        <img class="small top" src="../assets/img/s.png" :alt="smallTopAlt" loading="lazy" />
        <img class="small bottom" src="../assets/img/s.png" :alt="smallBottomAlt" loading="lazy" />
      </div>
    </div>

    <div class="text-area">
      <slot name="title">
        <h3 class="title">{{ title }}</h3>
      </slot>
      <slot name="content">
        <p class="content">{{ content }}</p>
      </slot>
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
  gap: 1.5rem;
  align-items: flex-start;
  border: black 1px solid;
}

.photos {
  display: flex;
  gap: 0.5rem;
  align-items: stretch;
}

.photos img {
  display: block;
  width: 20%;
  height: 20%;
  object-fit: cover;
  border-radius: 8px;
}

.large {
  width: 100px;
  height: 100px;
  flex-shrink: 0;
}

.small-stack {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  justify-content: space-between;
  border: red 1px solid;
}

.small {
  width: 160px;
  height: 156px;
  flex-shrink: 0;
}

.text-area {
  flex: 1;
  max-width: 500px;
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.title {
  margin: 0;
  font-size: 1.25rem;
  font-weight: 600;
}

.content {
  margin: 0;
  line-height: 1.6;
  color: var(--text-muted, #555);
}

/* Responsive: stack vertically on narrow screens */
@media (max-width: 800px) {
  .visited-photo {
    flex-direction: column;
    border: black 1px solid;
  }

  .photos {
    flex-direction: row;
    justify-content: center;
    gap: 0.75rem;
  }

  .large {
    width: 100%;
    max-width: 420px;
    height: 260px;
  }

  .small {
    width: 120px;
    height: 120px;
  }

  .text-area {
    max-width: 100%;
  }
}
</style>
