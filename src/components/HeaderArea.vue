<template>
  <el-header class="header">
    <el-button
      :icon="isSidebarOpen ? ArrowRight : ArrowLeft"
      circle
      @click="toggleSidebar"
    >
    </el-button>
  </el-header>
</template>

<script setup lang="ts">
import { computed } from 'vue'
import { ArrowLeft, ArrowRight } from '@element-plus/icons-vue'
import { useSidebarStore } from '@/stores/sidebarStore'

const sidebarStore = useSidebarStore()
const isSidebarOpen = computed(() => sidebarStore.isSidebarOpen)

const toggleSidebar = () => {
  sidebarStore.toggleSidebar()
}
</script>

<style lang="scss" scoped>
.header {
  display: flex;
  align-items: center;
}
</style>
