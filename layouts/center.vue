<template>
  <div class="slidev-layout center">
    <div class="header" v-if="headerEnable">
      <p>{{ headerTitle }}</p>
      <img :src="headerLogo" alt="logo" v-if="headerLogo" />
    </div>
    <div class="container">
      <slot />
    </div>
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
  
  .header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    height: 1.7rem;
    margin-bottom: 0.8rem;
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