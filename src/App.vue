<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import { useDark, useToggle } from '@vueuse/core'
import { Open } from '@element-plus/icons-vue'
const isDark = useDark()
const toggleDark = useToggle(isDark)
</script>

<template>
  <el-container>
    <el-header>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/about">About</RouterLink>
      <ElButton type="info" :icon="Open" circle @click="toggleDark()" />
    </el-header>
    <el-main><RouterView /></el-main>
  </el-container>
</template>

<style scoped></style>
