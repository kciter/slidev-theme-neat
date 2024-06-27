<template>
  <div class="spacer" :style="{ height: gap + 'px' }" />
</template>

<script setup>
import { defineProps } from 'vue'

const props = defineProps({
  gap: Number,
})
</script>