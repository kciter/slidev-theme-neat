<template>
  <figure class="flex flex-col items-center justify-center image">
    <img :src="src" :alt="caption" :width="width" :height="height" />
    <figcaption class="mt-3 text-center text-xs caption" v-if="caption">
      {{ caption }}
    </figcaption>
  </figure>
</template>

<script setup>
defineProps({
  src: String,
  width: [Number, String],
  height: [Number, String],
  caption: String
});
</script>

<style>
.image {
  .caption {
    color: var(--slidev-theme-text);
    opacity: 0.7;
  }
}
</style>