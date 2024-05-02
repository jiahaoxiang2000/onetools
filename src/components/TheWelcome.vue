<script setup lang="ts">
import { ref } from 'vue'
import { useCounterStore } from '../stores/counter'
let counterStore = useCounterStore()
let show = ref(true)
let checked = ref(false)
const selected = ref('A')

const options = ref([
  { text: 'One', value: 'A' },
  { text: 'Two', value: 'B' },
  { text: 'Three', value: 'C' }
])
</script>

<template>
  <select v-model="selected">
    <option v-for="op in options" :value="op.value" :key="op.value">
      {{ op.text }}
    </option>
  </select>

  <div>Selected: {{ selected }}</div>
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
