<!-- src/components/Signup.vue -->
<template>
  <div class="signup-container">
    <h2>Cadastro</h2>
    <form @submit.prevent="handleSignup">
      <label for="username">Usuário:</label>
      <input
        type="text"
        id="username"
        v-model="username"
        placeholder="Digite seu usuário"
        required
      />

      <label for="email">E-mail:</label>
      <input
        type="email"
        id="email"
        v-model="email"
        placeholder="Digite seu e-mail"
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

      <label for="confirmPassword">Confirmar Senha:</label>
      <input
        type="password"
        id="confirmPassword"
        v-model="confirmPassword"
        placeholder="Confirme sua senha"
        required
      />

      <button type="submit">Cadastrar</button>
    </form>

    <div v-if="message" class="message">{{ message }}</div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const username = ref('');
const email = ref('');
const password = ref('');
const confirmPassword = ref('');
const message = ref('');

const handleSignup = async () => {
  if (password.value !== confirmPassword.value) {
    message.value = 'As senhas não coincidem!';
    return;
  }

  try {
    // Simulação de chamada de API
    const response = await fetch('https://jsonplaceholder.typicode.com/posts', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
      },
      body: JSON.stringify({
        username: username.value,
        email: email.value,
        password: password.value,
      }),
    });

    const data = await response.json();
    if (response.ok) {
      message.value = 'Cadastro realizado com sucesso!';
      // Limpar campos após o cadastro bem-sucedido
      username.value = '';
      email.value = '';
      password.value = '';
      confirmPassword.value = '';
    } else {
      message.value = `Erro: ${data.message || 'Erro ao realizar o cadastro.'}`;
    }
  } catch (error) {
    message.value = 'Erro ao conectar ao servidor.';
    console.error('Erro:', error);
  }
};
</script>

<style scoped>
.signup-container {
  background-color: #fff;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  width: 300px;
  margin: auto;
  margin-top: 50px;
}

.signup-container input {
  width: 100%;
  padding: 10px;
  margin: 10px 0;
  border: 1px solid #ccc;
  border-radius: 4px;
}

.signup-container button {
  width: 100%;
  padding: 10px;
  background-color: #007bff;
  border: none;
  color: white;
  border-radius: 4px;
  cursor: pointer;
}

.signup-container button:hover {
  background-color: #0056b3;
}

.message {
  margin-top: 10px;
  color: #ff0000;
}
</style>