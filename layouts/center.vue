<template>
  <default class="center">
    <div class="container">
      <slot />
    </div>
  </default>
</template>

<script setup>
import Default from '../layouts/default.vue'
</script>

<style>
.slidev-layout.center {
  position: relative;
  @apply h-full;

  .container {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: auto;
    height: auto;
    text-align: center;
  }

  h1 {
    @apply text-4xl fw-700;
    color: var(--slidev-theme-text);
    margin: 0;
  }

  p {
    margin-top: 0.8rem;
    margin-bottom: 0.8rem;
  }
}
</style>