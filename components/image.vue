<template>
  <div class="image">
    <img :src="src" :alt="caption" :width="width" :height="height" />
    <figcaption class="mt-2 text-center text-xs caption" v-if="caption">
      {{ caption }}
    </figcaption>
  </div>
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
  display: inline-flex;
  flex-direction: column;

  .caption {
    color: var(--slidev-theme-dark-text);
    opacity: 0.8;
  }
}
</style>