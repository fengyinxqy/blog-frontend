<template>
  <el-container class="container">
    <AsideArea />
    <el-container direction="vertical">
      <HeaderArea />
      <el-main class="main-area">Main</el-main>
    </el-container>
  </el-container>
</template>

<script setup lang="ts">
import HeaderArea from '../components/HeaderArea.vue'
import AsideArea from '../components/AsideArea.vue'
</script>

<style lang="scss" scoped>
.container {
  height: 100vh;
}

.main-area {
  background-color: #f5f5f5;
}
</style>
