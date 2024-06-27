<template>
  <div class="columns">
    <slot />
  </div>
</template>

<script setup>
defineProps({
  cols: Number,
});
</script>

<style scoped>
.columns {
  display: grid;
  width: 100%;
  height: 100%;
  gap: 2rem;
  
  grid-template-columns: repeat(var(--cols, 2), 1fr);
}
</style>