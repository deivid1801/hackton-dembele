<script setup>

</script>

<template>
<header>
  <nav class="navbar">
    <div class="link-container">
    <router-link class="link">Inicio</router-link>
    <router-link class="link">Alugar</router-link>
    <router-link class="link">Login</router-link>
    <router-link class="link">Sing in</router-link>
    </div>
    
  </nav>


</header>

<div class="container">
    <div class="formulario">

    <label for="" >Nome do usuario:</label>
    <input class="input" type="text">

    <label for="">Email:</label>
    <input class="input" type="text">

    <label for="">Senha:</label>
    <input class="input" type="password">

    <label for="">Confime a senha:</label>
    <input class="input" type="password">

    <div class="row">
      <div class="item">
        <input class="radio" type="radio" value="masculino" id="masculino" />
          <label for="">Maculino</label>
      </div>
      <div class="item2">
        <input class="radio" type="radio" value="feminino" id="feminino" />
          <label for="">Feminino:</label>
      </div>
          
    </div>

    </div>
    
  </div>

</template>

<style scoped>

.navbar {
  background-color: #BC9270;
  width: 100%;
  height: 80px;
  display: flex;
  align-items: center;
}

.link {
  color: #fff;
  padding: 10px;
  text-decoration: none;
  transition: 0.3s;
}

.link:hover {
  color: black;
}

.link-container {
  display: flex;
  margin-left: auto;
  margin-right: 100px;
}

.container {
  display: flex;
  gap: 2rem;
  justify-content: center;
  margin-top: 4rem;
  
}

.formulario {
  border-radius: 20px;
  background-color: #F3EBDA;
  padding: 30px;
  width: 40%;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.input {
  padding: 10px;
  border: none;
  width: 500px;
  
  
}

label {
  margin-bottom: 5px;
  margin-right: auto;
  margin-left: 50px;
  margin-top: 20px;
}
</style>