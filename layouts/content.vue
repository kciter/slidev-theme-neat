<template>
  <div class="slidev-layout content">
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
@import url('https://fonts.googleapis.com/css2?family=Do+Hyeon&display=swap');

.slidev-layout.content {
  @apply h-full grid;

  h1 {
    @apply text-2xl fw-700;
    color: var(--slidev-theme-text);
    margin: 0;
    line-height: 1;
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

  h1 {
    font-family: "Do Hyeon", sans-serif;
    font-weight: 400;
    font-style: normal;
  }
}
</style>