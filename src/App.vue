<script setup>
import { ref } from 'vue';

    const nome = 'Gustavo'
    const idade = 16
    const contador = ref(0)
    const informações = 'Informações do usuário'

    function inverter(texto) {
        return texto.split('').reverse().join('')
    }

    function saudacao() {
        return `Olá, ${nome}!`
    }

    function incrementar(){
      contador.value++;
    }

    function decrementar(){
      if(contador.value > 0){
        contador.value--;
      }
    }

    function limpar(){
      contador.value = 0;
    }
</script>

<template>
    <div class="info">
        <h1>{{ informações }}</h1>
        <p>Nome: {{ nome }} </p>
        <p>Idade: {{ idade }}  anos</p>
        <hr />
        <p>Para completar 50 anos faltam: {{ 50 - idade }}  anos</p>
        <p>O nome tem {{ nome.length }}  caracteres</p>
        <p>O nome invertido é: {{ inverter(nome.toUpperCase()) }} </p>
        <hr />
        <p> Exemplo de saudação usando função</p>
        <p> {{ saudacao() }}  </p>

        <div class="contador">
      <h2>Contador</h2>
      <p>Valor: {{ contador }}</p>
      <button @click="incrementar()">incrementar</button>
      <button @click="decrementar()">decrementar</button>
      <button @click="limpar()">limpar</button>
      <div :style="{backgroundColor: contador > 10 ? 'green' : 'red' }">
        <p v-if="contador > 10">Valor maior que 10</p>
        <p v-else>Valor menor que 10</p>
      </div>
    </div>
    </div>

</template>

<style scoped>
.info, .contador {
  background-color: crimson;
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
}

h1, h2 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
}

button {
    margin: 10px;
    padding: 10px;
    border: 0;
    border-radius: 5px;
    background-color: white;
    color: black;
    font-weight: bold;
    cursor: pointer;
  }

  button:hover {
    background-color: gray;
  }

  div {
    margin: 10px 0;
    padding: 10px;
    border-radius: 5px;
    color: white;
    font-weight: bold;
  }
</style>