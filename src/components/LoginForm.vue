<template>
  <div class="login-container">
    <h2>Login</h2>
    <button @click="login">Login as Teacher</button>
  </div>
</template>

<script setup>
import { useRouter } from 'vue-router'
const router = useRouter()

function login() {
  // In a real app, validate here
  router.push('/dashboard')
}
</script>

<style scoped>
.login-container {
  max-width: 400px;
  margin: 100px auto;
  text-align: center;
}
</style>
