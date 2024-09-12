<template>
        <router-view></router-view>
    <div class="login-container">
      <h2>Login</h2>
      <form @submit.prevent="handleLogin">
        <label for="username">Usuário:</label>
        <input
          type="text"
          id="username"
          v-model="username"
          placeholder="Digite seu usuário"
          required
        />
  
        <label for="password">Senha:</label>
        <input
          type="password"
          id="password"
          v-model="password"
          placeholder="Digite sua senha"
          required
        />
  
        <button type="submit">Entrar</button>
      </form>
  
      <div v-if="message" class="message">{{ message }}</div>
  
      <router-link to="/singin">Não tem uma conta? Cadastre-se</router-link>
      
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const username = ref('');
  const password = ref('');
  const message = ref('');
  
  const handleLogin = async () => {
    try {
      // Simulação de chamada de API
      const response = await fetch('https://jsonplaceholder.typicode.com/posts', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
          username: username.value,
          password: password.value,
        }),
      });
  
      const data = await response.json();
      if (response.ok) {
        message.value = 'Login realizado com sucesso!';
        // Redirecionar para a página inicial ou outra página após o login
        // Exemplo: router.push('/home');
      } else {
        message.value = `Erro: ${data.message || 'Erro ao realizar o login.'}`;
      }
    } catch (error) {
      message.value = 'Erro ao conectar ao servidor.';
      console.error('Erro:', error);
    }
  };

  
  </script>
  
  <style scoped>
  .login-container {
    background-color: #fff;
    padding: 40px;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    width: 300px;
    margin: auto;
    margin-top: 50px;
  }
  
  .login-container input {
    width: 90%;
    padding: 10px;
    margin: 10px 0;
    border: 1px solid #ccc;
    border-radius: 4px;
  }
  
  .login-container button {
    width: 100%;
    padding: 10px;
    background-color: #007bff;
    border: none;
    color: white;
    border-radius: 4px;
    cursor: pointer;
  }
  
  .login-container button:hover {
    background-color: #0056b3;
  }
  
  .message {
    margin-top: 10px;
    color: #ff0000;
  }
  
  label {
    margin-left: 0;
  }
  </style>