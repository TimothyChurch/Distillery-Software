<script setup>
import { isCollapsed, toggleMenu } from '~/composables'
const router = useRouter()
</script>

<template>
  <el-menu
    :collapse="isCollapsed"
    class="side-menu"
  >
    <el-menu-item index="1" class="align-middle" @click="router.push('/user/dashboard')">
      <el-icon>
        <i-mdi-home />
      </el-icon>
      <template #title>
        Home
      </template>
    </el-menu-item>
    <el-menu-item index="2" @click="router.push('/user/inventory')">
      <el-icon>
        <i-ic-outline-inventory />
      </el-icon>
      <template #title>
        Inventory
      </template>
    </el-menu-item>
    <el-menu-item index="3" @click="router.push('/user/recipes')">
      <el-icon>
        <i-bi-card-list />
      </el-icon>
      <template #title>
        Recipes
      </template>
    </el-menu-item>
    <el-menu-item index="4" @click="router.push('/user/batches')">
      <el-icon>
        <i-ri-todo-line />
      </el-icon>
      <template #title>
        Batches
      </template>
    </el-menu-item>
  </el-menu>
</template>

<style>
.side-menu:not(.el-menu--collapse) {
  width: 200px;
  min-height: 400px;
}
</style>
