<script setup>
import { toggleRecipeAdd } from '~/composables'

const recipes = [
  {
    name: 'Recipe 1',
    type: 'Whiskey',
  },
  {
    name: 'Recipe 2',
    type: 'Whiskey',
  },
  {
    name: 'Recipe 3',
    type: 'Whiskey',
  },
  {
    name: 'Recipe 4',
    type: 'Gin',
  },
  {
    name: 'Recipe 5',
    type: 'Gin',
  },
  {
    name: 'Recipe 6',
    type: 'Gin',
  },
  {
    name: 'Recipe 7',
    type: 'Rum',
  },
  {
    name: 'Recipe 8',
    type: 'Rum',
  },
]
const filter = ref('')
const search = ref('')
const display = ref(true)
const filteredRecipes = () => {
  if (filter.value !== '')
    return recipes.filter(recipe => recipe.type === filter.value)
  else if (search.value !== '')
    return recipes.filter(recipe => recipe.name.toLowerCase().includes(search.value.toLowerCase()) || recipe.type.toLowerCase().includes(search.value.toLowerCase()))
  else
    return recipes
}

</script>

<template>
  <el-row justify="space-between">
    <el-col :span="2">
      <el-select v-model="filter" clearable>
        <el-option value="Whiskey" />
        <el-option value="Gin" />
        <el-option value="Rum" />
      </el-select>
    </el-col>
    <el-col :span="6">
      <el-input v-model="search" placeholder="Search...." clearable />
    </el-col>
    <el-col :span="2">
      <el-switch
        v-model="display"
        size="large"
        active-text="Card"
        inactive-text="Table"
      />
    </el-col>
    <el-col :span="2">
      <el-button round @click="toggleRecipeAdd">
        <el-icon>
          <i-bx-edit />
        </el-icon>
      </el-button>
    </el-col>
  </el-row>
  <el-row v-if="display" :gutter="10">
    <el-col v-for="recipe in filteredRecipes()" :key="recipe.name" :span="6" class="mt-5">
      <RecipeCard :recipe="recipe" />
    </el-col>
  </el-row>
  <el-table v-if="!display" :data="filteredRecipes()" width="100%">
    <el-table-column prop="name" label="Name" />
    <el-table-column prop="type" label="Type" />
  </el-table>
</template>
