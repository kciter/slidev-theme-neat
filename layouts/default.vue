<template>
  <div class="slidev-layout default">
    <div class="header" v-if="headerEnable">
      <p>{{ headerTitle }}</p>
      <img :src="headerLogo" alt="logo" v-if="headerLogo" />
    </div>
    <slot />
  </div>
</template>

<script setup>
const props = defineProps({
  headerEnable: Boolean,
  headerTitle: String,
  headerLogo: String,
});
</script>

<style>
.slidev-layout.default {
  @apply h-full;

  h1 {
    @apply text-2xl fw-700;
    line-height: 1;
  }
  
  .header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    height: 1.7rem;
    margin-bottom: 1.2rem;
    border-bottom: 0.5px solid #8FA7CA70;

    p {
      display: block;
      margin: 0;
      padding: 0;
      font-size: 0.7rem;
      font-weight: bold;
    }

    img {
      display: block;
      height: 1.3em;
    }
  }
}
</style>