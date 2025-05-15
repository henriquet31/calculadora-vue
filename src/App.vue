<script setup>
import { reactive, computed } from 'vue';

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
    <header class="p-5 mb-2 mt-4">
      <h1 class="text-center">Calculadora</h1>
    </header>
    <form>
      <div class="row justify-content-center">
        <div class="col-md-8">
          <select v-model="estado.operacao" class="form-select mb-3 text-center w-100">
            <option value="+">Soma</option>
            <option value="-">Subtração</option>
            <option value="*">Multiplicação</option>
            <option value="/">Divisão</option>
          </select>
        </div>
        <div class="col-md-8">
          <input v-model.number="estado.num1" type="number" class="form-control mb-3 text-center w-100" placeholder="Digite um número">
        </div>
        <div class="col-md-8">
          <input v-model.number="estado.num2" type="number" class="form-control mb-3 text-center w-100" placeholder="Digite um número">
        </div>
      </div>
    </form>
    <div class="mt-4 text-center">
      <h3>Resultado: {{ resultado }}</h3>
    </div>
  </div>
</template>

<style scoped>
</style>