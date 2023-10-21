<script setup>
import { reactive } from 'vue';

import Cabecalho from './components/Cabecalho.vue'
import Resultado from './components/Resultado.vue'
import Formulario from './components/Formulario.vue'

  const estado = reactive({
    numero1: 0,
    numero2: 0,
    operacao: '+'
  }) 

  const atualizaNumero1 = evento => estado.numero1 = Number(evento.target.value)
  const atualizaNumero2 = evento => estado.numero2 = Number(evento.target.value)
  const trocaOperacao = evento => estado.operacao = evento.target.value

  const calculaResultado = () => {
    switch (estado.operacao){
      case '+':
        return estado.numero1 + estado.numero2
      case '-':
        return estado.numero1 - estado.numero2
      case '*':
        return estado.numero1 * estado.numero2
      case '/':
        return estado.numero1 / estado.numero2
    }
  }

</script>

<template>
  <div class="container">
    <Cabecalho />

    <div class="calculadora rounded-3 p-5">
      <Resultado :resultado="calculaResultado()" />
      <Formulario :numero1 ="atualizaNumero1" :numero2="atualizaNumero2" :operacao="trocaOperacao" />

    </div>

  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Monofett&family=VT323&display=swap');

*{
  font-family: 'Monofett', monospace;
  font-family: 'VT323', monospace;
  letter-spacing: 5px;
  font-size: 30px;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.calculadora{
  background-color: rgba(122, 171, 159, 0.69);
}

</style>
