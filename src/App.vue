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
      <el-row>
        <el-col :span="16">
          <el-space size="large">
            <RouterLink to="/">Home</RouterLink>
            <RouterLink to="/about">About</RouterLink>
          </el-space>
        </el-col>
        <el-col :span="8" style="text-align: right" :gutter="10">
          <el-space size="large">
            <span v-if="isDark">Dark</span>
            <span v-else>Light</span>
            <ElButton type="info" :icon="Open" circle @click="toggleDark()" />
          </el-space>
        </el-col>
      </el-row>
    </el-header>
    <el-main><RouterView /></el-main>
  </el-container>
</template>

<style scoped></style>
