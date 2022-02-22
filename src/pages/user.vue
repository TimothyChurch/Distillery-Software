<script setup>

</script>

<template>
  <el-container>
    <el-aside width="auto">
      <SideMenu />
    </el-aside>
    <el-main class="!p-0">
      <el-container>
        <el-header>
          <SiteHeader />
        </el-header>
        <el-main>
          <router-view />
          <Dialogs />
        </el-main>
      </el-container>
    </el-main>
  </el-container>
</template>
