<script setup>

  import { reactive } from 'vue';
  import Cabecalho from './components/Cabecalho.vue'
  import Calculos from './components/Calculos.vue'


  const estado = reactive({
    operacao: '+',
    campo1: 0,
    campo2: 0,
    campoResultado: 0
    
  })

  
  let soma = () => {
    return estado.campoResultado = Number(estado.campo1 + estado.campo2)
  }

  let subtrai = () => {
    return estado.campoResultado = estado.campo1 - estado.campo2
  }

  let multiplica = () => {
    return estado.campoResultado = estado.campo1 * estado.campo2
  }

  let divide = () => {
    return estado.campoResultado = estado.campo1 / estado.campo2
  }

  const selecionaOperacao = () => {
    const {operacao} = estado

    switch (operacao) {
      case '+':
        return soma()
      case '-':
        return subtrai()
      case 'x':
        return multiplica()
      default:
        return divide()  
    }
  }
  
</script>

<template>
  <div class="container">
    <Cabecalho/>
    <Calculos :campo1="event => (estado.campo1 = Number(event.target.value))" :operacao="event => (estado.operacao = event.target.value)" :campo2="event => (estado.campo2 = Number(event.target.value))" :seleciona-operador="selecionaOperacao()"/>
  </div> 
</template>


