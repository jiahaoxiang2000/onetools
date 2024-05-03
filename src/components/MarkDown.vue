<template>
  <MdPreview v-model="model" :theme="theme" previewTheme="github" codeTheme="github" />
</template>

<script setup lang="ts">
import { computed, ref } from 'vue'
import { useDark } from '@vueuse/core'
import { MdPreview } from 'md-editor-v3'

const props = defineProps({
  context: String
})

let model = ref(props.context)

const isDark = useDark()
const theme = computed(() => (isDark.value ? 'dark' : 'light'))
</script>
