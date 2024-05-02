<script setup lang="ts">
import { ref } from 'vue'
import { useCounterStore } from '../stores/counter'
let counterStore = useCounterStore()
let show = ref(true)
</script>

<template>
  <a v-if="show">{{ counterStore.count }} {{ counterStore.doubleCount }}</a>
  <button @click="counterStore.increment">Increment</button>
  <button
    @click="
      () => {
        show = !show
      }
    "
  >
    show
  </button>
</template>
