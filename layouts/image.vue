<template>
  <default class="image"
  :style="{ backgroundImage: `url(${image})`, backgroundSize: backgroundSize }"
  >
    <slot />
  </default>
</template>

<script setup>
import Default from '../layouts/default.vue'

const props = defineProps({
  image: String,
  backgroundSize: {
    type: String,
    default: 'cover',
  },
});
</script>

<style scoped>
.slidev-layout.image {
  .background {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    overflow: hidden;
  }

  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}
</style>