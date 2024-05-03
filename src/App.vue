<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import { useDark, useToggle } from '@vueuse/core'
import IconEpApple from '~icons/ep/apple'
const isDark = useDark()
const toggleDark = useToggle(isDark)
</script>

<template>
  <el-container>
    <el-header>
      <RouterLink to="/">Home test</RouterLink>
      <RouterLink to="/about">About</RouterLink>
      <ElButton :icon="IconEpApple" @click="toggleDark()" />
    </el-header>
    <el-main><RouterView /></el-main>
  </el-container>
</template>

<style scoped></style>
