<template>
  <default class="two-cols">
    <slot />
    
    <div class="container">
      <div class="left">
        <slot name="left" />
      </div>
      <div class="right">
        <slot name="right" />
      </div>
    </div>
  </default>
</template>

<script setup>
import Default from '../layouts/default.vue'
</script>

<style scoped>
.slidev-layout.two-cols {
  .container {
    display: flex;
    gap: 2rem;
    height: 100%;
  }

  .left {
    flex: 1;
  }

  .right {
    flex: 1;
  }
}
</style>