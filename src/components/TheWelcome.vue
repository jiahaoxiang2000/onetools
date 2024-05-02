<script setup lang="ts">
import { useCounterStore } from '../stores/counter'
let counterStore = useCounterStore()
</script>

<template>
  <a>{{ counterStore.count }} {{ counterStore.doubleCount }}</a>
  <button @click="counterStore.increment">Increment</button>
</template>
