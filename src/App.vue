<script setup>
  import { reactive } from "vue";
  import Cabecalho from "./components/Cabecalho.vue";
  import Corpo from "./components/Corpo.vue";

  const estado = reactive({
    numero1: 0,
    numero2: 0,
    operacao: "adicao"
  })

  const armazenaN1 = (e) => {
    return estado.numero1 = e.target.value
  }

  const armazenaN2 = (e) => {
    return estado.numero2 = e.target.value
  }

  const recuperaEscolha = (e) => {
    return estado.operacao = e.target.value
  }

  const operacaoAritimetica = function () {
    switch (estado.operacao) {
      case "adicao":
        return parseInt(estado.numero1) + parseInt(estado.numero2);
      case "subtracao":
        return estado.numero1 - estado.numero2;
      case "multiplicacao":
        return estado.numero1 * estado.numero2;
      default:
        return estado.numero1 / estado.numero2;
    }
  }

</script>

<template>
  <div class="container">
    <Cabecalho />
    <Corpo :resultado="operacaoAritimetica()" :n1="armazenaN1" :n2="armazenaN2" :escolha="recuperaEscolha" />
  </div>
</template>

<style scoped>
  *{
    box-sizing: border-box;
    font-family: Arial, Helvetica, sans-serif;
  }

  .container{
    max-width: 1024px;
    width: 100%;
    margin: auto;
    padding: 3.2vw;
  }

</style>
