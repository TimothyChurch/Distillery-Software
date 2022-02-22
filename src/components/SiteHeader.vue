<script setup>
import { isCollapsed, toggleDark, toggleMenu } from '~/composables'

</script>

<template>
  <el-row justify="space-between">
    <el-col :span="2">
      <el-button round @click="toggleMenu()">
        <i-mdi-arrow-left v-if="!isCollapsed" />
        <i-mdi-arrow-right v-if="isCollapsed" />
      </el-button>
    </el-col>
    <el-col :span="2" class="justify-end">
      <el-button round @click="toggleDark()">
        <i-mdi-cog />
      </el-button>
    </el-col>
  </el-row>
</template>
