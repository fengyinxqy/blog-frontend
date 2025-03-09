<template>
  <el-aside :width="asideWidth">
    <div class="logo">Blog</div>
    <el-menu
      default-active="/"
      class="el-menu-vertical"
      :collapse="isSidebarOpen"
      router
    >
      <el-menu-item
        v-for="menu in menuList"
        :key="menu.index"
        :index="menu.index"
      >
        <el-icon>
          <component :is="menu.icon" />
        </el-icon>
        <span>{{ menu.title }}</span>
      </el-menu-item>
    </el-menu>
  </el-aside>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'
import { useSidebarStore } from '@/stores/sidebarStore'

import { Document, Folder } from '@element-plus/icons-vue'

const menuList = ref([
  {
    title: '文章列表',
    index: '/',
    icon: Document,
  },
  {
    title: '分类列表',
    index: '/category',
    icon: Folder,
  },
])

const sidebarStore = useSidebarStore()
const isSidebarOpen = computed(() => sidebarStore.isSidebarOpen)

// 计算侧边栏宽度
const asideWidth = computed(() => (isSidebarOpen.value ? '64px' : '200px'))
</script>

<style lang="scss" scoped>
.el-aside {
  display: flex;
  flex-direction: column;
  transition: width 0.3s ease;
  background-color: #f5f5f5;
}

.el-menu-vertical {
  flex: 1;
  position: relative;
  height: 100%;
  background-color: #f5f5f5;
}

.logo {
  font-size: 20px;
  height: 60px;
  display: flex;
  align-items: center;
  padding-left: 20px;
  border-bottom: 1px solid #e6e6e6;
  box-sizing: border-box;
}
</style>
