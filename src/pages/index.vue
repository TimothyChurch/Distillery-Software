<script setup>
const router = useRouter()
const email = ref('')
const password = ref('')

const login = () => {
  router.push('/user/dashboard')
}
</script>

<template>
  <el-card>
    <el-input v-model="email" placeholder="Email" />
    <el-input v-model="password" placeholder="Password" />
    <el-button @click="login()">
      Log In
    </el-button>
  </el-card>
</template>
