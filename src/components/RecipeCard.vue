<script setup>
const props = defineProps({
  recipe: {
    type: Object,
  },
})
</script>

<template>
  <el-card>
    <h1>{{ recipe.name }}</h1>
    <p>{{ recipe.type }}</p>
  </el-card>
</template>
