<script setup>
import { ref } from 'vue';

    const nome = 'Nathaly'
    const idade = 16
    const contador = ref(0)
    const informações = 'Informações do usuário'
    const email = 'nathalycarolineadaoo@gmail.com'
    const número = 4791422026
    

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

    function multiplicar(){
      const vezes = Number(prompt("Informe um número para multiplicar"))
      contador.value = contador.value * vezes; 
    }

    function dividir(){
      const dividir = Number(prompt("Informe um número para dividir"))
      contador.value = contador.value / dividir;
    }

    function limpar(){
      contador.value = 0;
    }
</script>

<template>
  <div class="conteudo">
    <div class="info">
        <h1>{{ informações }}</h1>
        <p>Nome: {{ nome }} </p>
        <p>Idade: {{ idade }}  anos</p>
        <p>Email: {{ email }}</p>
        <p>Número de telefone: {{ número }}</p>menor que 10
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
      <button @click="multiplicar()">vezes</button>
      <button @click="dividir()">divisão</button>
      <button @click="limpar()">limpar</button>
      <div :style="{backgroundColor: contador % 2 === 0 ? 'green' : 'red'}">
        <p v-if="contador % 2 === 0">Valor é par</p>
        <p v-else>Valor é ímpar</p>
      </div>
    </div>
    </div>
  </div>
</template>

<style scoped>
  .conteudo{
    margin: 0px 0px 0px 300px;
    min-width: 600px;
  }
  .info,
  .contador {
    background-color: mediumturquoise;
    padding: 20px 30px;
    color: black;
    border-radius: 10px;
  }

  h1 {
    color: white;
    font-weight: bold;
    font-size: 1.5em;
  }

  button {
    margin: 10px;
    padding: 10px;
    border: 0;
    border-radius: 5px;
    background-color: lightblue;
    color: black;
    font-weight: bold;
    cursor: pointer;
  }

  button:hover {
    background-color: cadetblue;
  }

  div {
    margin: 10px 0;
    padding: 10px;
    border-radius: 5px;
    color: black;
    font-weight: bold;
  }
  
</style>