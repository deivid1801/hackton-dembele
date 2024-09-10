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
    
    </template>
    <style scoped>
.navbar {
  background-color: #676767;
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

.input {
  padding: 10px;
  border: none;
  width: 300px;
  
  
}

label {
  margin-bottom: 5px;
  margin-right: auto;
  margin-left: 50px;
  margin-top: 20px;
}</style>