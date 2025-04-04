<template>
    <div class="column">
      <div class="form-container">
        <p>Adicionar Jogador</p>
        <input
            ref="inputJogador" 
            v-model="novoJogador" 
            type="text" 
            placeholder="Nome do jogador"
            @keyup.enter="adicionarJogador"
        />
        <button @click="adicionarJogador">Adicionar</button>
  
        <ul v-if="jogadores.length > 0" class="lista-jogadores">
          <li v-for="(jogador, index) in jogadores" :key="index">
            {{ jogador }}
            <button @click="removerJogador(index)">❌</button>
          </li>
        </ul>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        novoJogador: "",
        jogadores: [], // Lista de jogadores adicionados
      };
    },
    methods: {
      adicionarJogador() {
        if (this.novoJogador.trim() !== "") {
        const nome = this.novoJogador.trim();
        this.jogadores.push(nome);
        this.$emit("adicionarJogador", nome);
        this.novoJogador = "";

        // foca no input novamente
        this.$refs.inputJogador.focus();
        }
      },
      removerJogador(index) {
          this.jogadores.splice(index, 1);
          const jogadorRemovido = jogadores.value[index];
      },
    },
    mounted() {
      this.$refs.inputJogador.focus();
    }
  };
  </script>
  
  <style scoped>
  .column {
    flex: 1;
    display: flex;
    align-items: center;
    justify-content: center;
    /* border: 1px solid #ddd;
    background-color: #f8f9fa; */
  }
  
  .form-container {
    display: flex;
    width: 90%;
    height: 90%;
    flex-direction: column;
    gap: 10px;
    text-align: center;
    /* background-color:red; */
  }
  
  input {
    padding: 8px;
    font-size: 16px;
    border: 1px solid #ccc;
    border-radius: 4px;
  }
  
  button {
    padding: 8px;
    background: #28a745;
    color: white;
    border: none;
    cursor: pointer;
    border-radius: 4px;
  }
  
  button:hover {
    background: #218838;
  }
  
  .lista-jogadores {
    margin-top: 10px;
    padding: 0;
    list-style: none;
    overflow-y: auto
  }
  
  .lista-jogadores li {
    background: #fff;
    padding: 8px;
    margin-top: 5px;
    border: 1px solid #ccc;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .lista-jogadores button {
    background: rgb(239, 187, 187);
    border: none;
    color: white;
    padding: 5px;
    cursor: pointer;
    border-radius: 4px;
  }
  
  .lista-jogadores button:hover {
    background: darkred;
  }
  </style>
  