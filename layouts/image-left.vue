<template>
  <div class="slidev-layout image-left">
    <div class="image">
      <img :src="image" alt="image" />
    </div>
    <div class="content">
      <div class="header" v-if="headerEnable">
        <p>{{ headerTitle }}</p>
        <img :src="headerLogo" alt="logo" v-if="headerLogo" />
      </div>
      <slot />
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  headerEnable: Boolean,
  headerTitle: String,
  headerLogo: String,
  image: String
});
</script>

<style scoped>
.slidev-layout.image-left {
  @apply h-full;

  display: flex;
  gap: 2rem;

  h1 {
    @apply text-2xl;
    line-height: 1;
  }

  h2 {
    @apply text-xl;
    line-height: 1;
  }

  h3 {
    @apply text-lg;
    line-height: 1;
  }

  h4 {
    @apply text-base;
    line-height: 1;
  }

  h5 {
    @apply text-sm;
    line-height: 1;
  }
}

.image {
  @apply h-full;
  flex: 1;
  max-width: 50%;
}

.image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.content {
  @apply h-full;
  flex: 1;
}

.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  height: 24px;
  margin-bottom: 1.2rem;
  border-bottom: 0.5px solid var(--slidev-theme-light-divider);

  p {
    display: block;
    margin: 0;
    padding: 0;
    font-size: 0.7rem;
    font-weight: bold;
  }

  img {
    display: block;
    height: 0.6em;
  }
}

html.dark {
  .slidev-layout.image-left {
    .header {
      border-bottom: 0.5px solid var(--slidev-theme-dark-divider);
    }
  }
}
</style>