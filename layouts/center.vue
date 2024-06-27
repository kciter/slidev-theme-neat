<template>
  <default class="center" :headerEnable="headerEnable">
    <div class="h-full grid place-content-center text-center">
      <div class="my-auto" v-bind:style="{ marginTop: headerEnable ? '-76px' : '0' }">
        <slot />
      </div>
    </div>
  </default>
</template>

<script setup>
import Default from '../layouts/default.vue'

const props = defineProps({
  headerEnable: Boolean,
});
</script>

<style>
.slidev-layout.center {
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