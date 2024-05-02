<script setup lang="ts">
import { ref } from 'vue'
import { useCounterStore } from '../stores/counter'
let counterStore = useCounterStore()
let show = ref(true)
let checked = ref(false)
</script>

<template>
  <a v-if="show">{{ counterStore.count }} {{ counterStore.doubleCount }}</a>
  <button @click="counterStore.increment">Increment</button>
  <input type="checkbox" id="checkbox" v-model="checked" />
  <label for="checkbox">{{ checked }}</label>
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
