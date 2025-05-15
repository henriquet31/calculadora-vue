<script setup>
import { reactive, computed } from 'vue';
import Cabecalho from './components/cabecalho.vue';
import Formulario from './components/formulario.vue';
import Resultado from './components/resultado.vue';

const estado = reactive({
  num1: 0,
  num2: 0,
  operacao: ''
});

const resultado = computed(() => {
  const { num1, num2, operacao } = estado;
  switch (operacao) {
    case '+':
      return num1 + num2;
    case '-':
      return num1 - num2;
    case '*':
      return num1 * num2;
    case '/':
      return num2 !== 0 ? num1 / num2 : 'Erro (divisão por zero)';
    default:
      return 'Operação inválida';
  }
});
</script>

<template>
  <div class="container pb-5 bg-light rounded-3 shadow-sm" style="max-width: 600px;">
    <Cabecalho />
    <Formulario :estado="estado" />
    <Resultado :resultado="resultado" />
    
  </div>
</template>

<style scoped>
</style>