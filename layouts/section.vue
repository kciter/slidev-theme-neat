<template>
  <div class="slidev-layout section">
    <div class="header" v-if="headerEnable">
      <p>{{ headerTitle }}</p>
      <img :src="headerLogo" alt="logo" v-if="headerLogo" />
    </div>
    <h1 class="title">
      {{ subject }}
    </h1>
  </div>
</template>

<script setup>
const props = defineProps({
  headerEnable: Boolean,
  headerTitle: String,
  headerLogo: String,
  subject: String,
});
</script>

<style>
.slidev-layout.section {
  position: relative;
  @apply h-full;

  .title {
    @apply text-4xl fw-700;

    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: auto;
    height: auto;
    text-align: center;
    color: var(--slidev-theme-text);
    margin: 0;

    p { margin: 0 }

    &::before {
      content: '';
      position: absolute;
      top: -20px;
      left: -64px;
      display: block;
      width: 40px;
      height: 1px;
      background-color: var(--slidev-theme-text);
      margin-bottom: 1.2rem;
      transform: rotate(-30deg);
    }

    &::after {
      content: '';
      position: absolute;
      bottom: -36px;
      right: -64px;
      display: block;
      width: 40px;
      height: 1px;
      background-color: var(--slidev-theme-text);
      margin-bottom: 1.2rem;
      transform: rotate(-30deg);
    }
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