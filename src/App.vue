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
            <el-link href="/"> Home </el-link>
            <el-link href="/about"> About </el-link>
          </el-space>
        </el-col>
        <el-col :span="8" style="text-align: right" :gutter="10">
          <el-space size="large">
            <el-text v-if="isDark">Dark</el-text>
            <el-text v-else>Light</el-text>
            <ElButton type="info" :icon="Open" circle @click="toggleDark()" />
          </el-space>
        </el-col>
      </el-row>
    </el-header>
    <el-main><RouterView /></el-main>
  </el-container>
</template>

<style scoped></style>
