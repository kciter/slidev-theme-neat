<template>
  <div class="slidev-layout bullets">
    <div>
      <div class="header">
        <p>{{ headerLeft }}</p>
        <p>{{ headerLeft }}</p>
      </div>
      <slot />
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  'headerLeft': String,
});
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Do+Hyeon&display=swap');

.bullets {
  .header {
    display: flex;
    justify-content: space-between;
    width: '100%';
    margin-bottom: 1rem;
    border-bottom: 0.5px solid #8FA7CA70;
    font-size: 0.7rem;
    font-weight: bold;

    p {
      margin: 0;
    }
  }

  h1 {
    font-family: "Do Hyeon", sans-serif;
    font-weight: 400;
    font-style: normal;
  }
}
</style>