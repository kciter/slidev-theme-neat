<template>
  <div class="slidev-layout cover">
    <div class="background">
      <div class="circle-1" />
      <div class="circle-2" />
      <div class="circle-3" />
    </div>

    <div class="container">
      <img class="logo" :src="coverLogo" alt="cover logo" v-if="coverLogo" />
      <h1 class="title">{{ coverTitle }}</h1>
      <hr />
      <h2 class="author">{{ coverAuthor }}</h2>

      <div class="description">
        <slot />
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  coverTitle: String,
  coverAuthor: String,
  coverLogo: String,
});
</script>

<style>
.slidev-layout.cover {
  .background {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 0;
    filter: blur(3px);

    .circle-1 {
      position: absolute;
      top: -360px;
      right: -120px;
      width: 900px;
      height: 680px;
      border-radius: 50%;
      background-color: #A5D7A7;
      opacity: 0.11;
    }

    .circle-2 {
      position: absolute;
      bottom: -360px;
      right: -320px;
      width: 900px;
      height: 650px;
      border-radius: 50%;
      background-color: #7FBBFF;
      opacity: 0.15;
    }

    .circle-3 {
      position: absolute;
      top: -560px;
      right: -650px;
      width: 1050px;
      height: 950px;
      border-radius: 50%;
      background-color: #F9A19A;
      opacity: 0.2;
      
    }
  }

  .container {
    position: relative;
    margin-top: 100px;
    z-index: 1;
  }

  img.logo {
    width: auto;
    height: 30px;
    display: block;
    margin-bottom: 8px;
  }

  h1.title {
    font-size: 2.5rem;
    line-height: 1;
    margin-bottom: 0;
  }

  h2.author {
    font-size: 0.9rem;
    line-height: 1;
    font-weight: 100;
  }

  hr {
    width: 160px;
    margin-top: 12px;
    margin-bottom: 24px;
    height: 1px;
    background-color: black !important;
  }

  .description {
    margin-top: 40px;
    font-size: 1rem;
    line-height: 1.5;
  }
}

.dark {
  .slidev-layout.cover {
    .background {
      mix-blend-mode: luminosity;
    }

    hr {
      background-color: white !important;
    }
  }
}
</style>