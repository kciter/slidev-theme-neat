<template>
  <default class="section">
    <h1 class="title">
      {{ subject }}
    </h1>
  </default>
</template>

<script setup>
import Default from '../layouts/default.vue'

const props = defineProps({
  subject: String,
});
</script>

<style scoped>
.slidev-layout.section {
  .title {
    @apply text-4xl fw-700;

    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: auto;
    height: auto;
    text-align: center;
    margin: 0;

    &::before {
      content: '';
      position: absolute;
      top: -14px;
      left: -64px;
      display: block;
      width: 40px;
      height: 1px;
      background-color: var(--slidev-theme-light-text);
      margin-bottom: 1.2rem;
      transform: rotate(-30deg);
    }

    &::after {
      content: '';
      position: absolute;
      bottom: -30px;
      right: -64px;
      display: block;
      width: 40px;
      height: 1px;
      background-color: var(--slidev-theme-light-text);
      margin-bottom: 1.2rem;
      transform: rotate(-30deg);
    }
  }
}
.dark {
  .slidev-layout.section {
    .title {
      &::before {
        background-color: var(--slidev-theme-dark-text);
      }

      &::after {
        background-color: var(--slidev-theme-dark-text);
      }
    }
  }
}
</style>