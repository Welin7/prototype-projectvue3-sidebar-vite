<template>
    <div class="login-container">
      <img src="@/assets/logo_finance.png" alt="Logo" class="logo" />
      <h1>Login</h1>
      <form @submit.prevent="login">
        <div>
          <label for="email">Email:</label>
          <input type="email" v-model="email" id="email" required />
        </div>
        <div>
          <label for="password">Password:</label>
          <input type="password" v-model="password" id="password" required />
        </div>
        <button type="submit">Login</button>
      </form>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  import { useRouter } from 'vue-router'
  
  const email = ref('')
  const password = ref('')
  const router = useRouter()
  
  const login = () => {
    if (email.value === 'user@example.com' && password.value === 'password') {
      alert('Login Sucess!')
      router.push('/home')
    } else {
      alert('Email or Password incorrects.')
    }
  }
  </script>
  
  <style scoped>
  .login-container {
    max-width: 800px;
    margin: 100px auto;
    padding: 30px;
    border: 1px solid #ccc;
    border-radius: 10px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  }

  .logo {
    width: 256px;
    margin-bottom: 40px; 
  }
  
  h1 {
    text-align: center;
    margin-bottom: 20px;
  }
  
  label {
    display: block;
    margin-bottom: 5px;
  }
  
  input {
    width: 100%;
    padding: 8px;
    margin-bottom: 10px;
    border-radius: 5px;
    border: 1px solid #ccc;
  }
  
  button {
    width: 100%;
    padding: 10px;
    background-color: #42b983;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #3a9b71;
  }
  </style>
  