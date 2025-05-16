<script setup>
import { ref } from 'vue';
import FormJogador from './FormJogador.vue';
import Config from './Config.vue';
import Result from './Result.vue';

const jogadores = ref([]); // Lista centralizada

const adicionarJogador = (nome) => {
  jogadores.value.push(nome);
  console.log(jogadores.value)
  console.log('jogadores acima')
};

const removerJogador = (nome) => {
  jogadores.value = jogadores.value.filter(jogador => jogador !== nome);
  console.log('teste aqui?')
};
</script>

<template>
  <main class="main">
    <FormJogador 
      @adicionar-jogador="adicionarJogador" 
      @remover-jogador="removerJogador"
    />
    <Config :jogadores="jogadores" /> 
    <Result :jogadores="jogadores" />
  </main>
</template>

<style scoped>
.main {
  display: flex;
  width: 100%;
  margin: auto;
  height: 85vh;
  background-color: white;
  color: black; /* O resto da altura depois do header */
}
</style>
