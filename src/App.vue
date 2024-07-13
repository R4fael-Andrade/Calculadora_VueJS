<script setup>
import { reactive, watch } from 'vue';
import  Corpo from './components/Corpo.vue';
  const estado = reactive ({
    numero1: 0,
    numero2: 0,
    resultado: 0,
    operacoes: 'somar',
  })

  const escolheOperacao = () => {
    const {operacoes} = estado; 

    switch (operacoes) {
      case 'somar':
          estado.resultado = parseFloat(estado.numero1) + parseFloat(estado.numero2);
          break;
      case 'subtrair':
          estado.resultado = parseFloat(estado.numero1) - parseFloat(estado.numero2);
          break;
      case 'multiplicar':
          estado.resultado = parseFloat(estado.numero1) * parseFloat(estado.numero2);
          break;
      case 'dividir':
          estado.resultado = parseFloat(estado.numero1) / parseFloat(estado.numero2);
          break;
      default: 
          estado.resultado  = 0;
      }
      return estado.resultado;
      
  }

  watch(
    () => [estado.numero1, estado.numero2, estado.operacoes],
    escolheOperacao
  )

</script>

<template>
    <div class="container bg-light">
      <Corpo :tipo-operacao="evento => estado.operacoes = evento.target.value" :valorn2="evento => estado.numero2 = evento.target.value" :valorn1="evento => estado.numero1 = evento.target.value" :get-operacao="escolheOperacao()" />
    </div>
</template>

<style scoped>

</style>
