<template>
  <main>
    <el-text size="large" tag="b">OneTools: More Than Just One Tool</el-text>
    <el-divider />
    <el-container style="flex-direction: column">
      <el-card style="margin-bottom: 20px">
        <template #header>
          <el-link href="/photo">
            <el-text tag="b" size="large">Identification photos</el-text>
          </el-link>
        </template>

        <el-text>
          Sometime you need to identify a person from a photo. However, you only have some lifestyle
          photos. This tool will help you create an identification photo from the lifestyle photo.
        </el-text>
      </el-card>
    </el-container>
  </main>
</template>

<script setup lang="ts"></script>
