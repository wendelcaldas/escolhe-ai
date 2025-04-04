<template>
    <div class="column">
      <div class="config-container">
        <h2 class="config-titulo">Tipo de Campo</h2>
        <section class="config-container-button">
            <button>Futebol</button>
            <button>Futsal</button>
            <button>Basquete</button>
        </section>
        <h2 class="config-titulo">Jogadores por Time</h2>
        <input type="number" name="" id="num-jogadores" min="2" max="11" value="5">
        <h2 class="config-titulo">Em caso de não fechar times você prefere:</h2>
        <div>
          <label>
            <input type="radio" name="escolha" value="opcao1" v-model="opcaoSelecionada" />
            Dividir a sobra entre os times
          </label>
      
          <label>
            <input type="radio" name="escolha" value="opcao2" v-model="opcaoSelecionada" />
            Formar um time incompleto
          </label>
        </div>
      </div>
    </div>
  </template>

  <script setup>
  defineProps({
    jogadores: Array, // Declarando que a prop 'jogadores' é um array
  });
  </script>

  <style scoped>
  .column {
    flex: 1; /* Faz as colunas terem tamanhos iguais */
    display: flex;
    align-items: center;
    justify-content: center
  }
  .config-container{
    /* background-color: gray; */
    width: 90%;
    height: 90%;
    display: flex;
    flex-direction: column;
    align-items: center;
    /* justify-content: center; */
  }
  .config-titulo{
    font-weight: bold;
    columns: black;
    margin:20px;
    text-align: center;
  }
  .config-container-button{
    /* background-color: red; */
    width: 90%;
    display: flex;
    justify-content: space-around;
  }

  .config-container-button button {
    /* background-color: blue; */
    /* border: none; */
    width: 30%;
    height: 40px;
  }
  .config-container-button button:hover {
    cursor: pointer;
  }
  #num-jogadores{
    width: 20%;
    height: 40px;
    font-size: 24px;
    text-align: center;
    font-weight: bold;
  }
  </style>
  