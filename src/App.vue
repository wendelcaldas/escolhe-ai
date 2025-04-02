<script setup>
import Header from './components/Header.vue';
import Main from './components/Main.vue';
</script>

<template>
  <div class="app-container">
    <Header />
    <Main />  
  </div>
</template>

<style>
/* Faz com que a div principal ocupe 100% da altura da tela */
html, body, #app {
  height: 100%;
  width: 100%;
  margin: 0;
  padding: 0; 
}

.app-container {
  display: flex;
  flex-direction: column; /* Garante que os elementos fiquem em coluna */
  height: 100vh; /* Ocupa a altura total da tela */
  width: 100vw;
}
</style>
