<template>
  <div>
    <el-container>
      <el-row style="width: 100%" :gutter="20">
        <el-col :span="12">
          <el-image id="originFigure" :src="url" fit="fill" />
        </el-col>
        <el-col :span="12">
          <canvas id="canvasOutput"></canvas>
        </el-col>
      </el-row>
    </el-container>
    <el-upload style="margin: 20px" :auto-upload="false" :on-change="handleChange" :limit="1">
      <template #trigger>
        <el-button type="primary">import</el-button>
      </template>
      <el-button style="margin-left: 10px" type="success" @click="transform"> transform </el-button>
    </el-upload>
  </div>
</template>

<script setup lang="ts">
import { type UploadProps, type UploadRawFile } from 'element-plus'
import cv from '@techstark/opencv-js'

let url = ref<string>('')
let imageFile = ref<UploadRawFile | null>(null)

const handleChange: UploadProps['onChange'] = (file) => {
  const reader = new FileReader()
  imageFile.value = file.raw as UploadRawFile

  reader.onload = (e) => {
    if (e.target) {
      url.value = e.target.result as string
    }
  }
  reader.readAsDataURL(file.raw as UploadRawFile)
}

const transform = () => {
  let src = cv.imread('originFigure')
  let dst = new cv.Mat()
  let rect = new cv.Rect(200, 200, 200, 200)
  dst = src.roi(rect)
  cv.imshow('canvasOutput', dst)
  src.delete()
  dst.delete()
}
</script>

<style scoped></style>
