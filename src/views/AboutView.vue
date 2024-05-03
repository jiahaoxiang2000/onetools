<template>
  <MarkDown :context />
</template>

<script setup lang="ts">
import aboutStr from '../assets/about.md?raw'
import MarkDown from '@/components/MarkDown.vue'

const context = ref(aboutStr)
</script>

<style></style>
