<script setup>
import { defineProps } from 'vue';

const props = defineProps(['estado']);
</script>

<template>
    <form>
        <div class="row justify-content-center">
            <div class="col-md-8">
                <select v-model="props.estado.operacao" class="form-select mb-3 text-center w-100">
                <option value="+">Soma</option>
                <option value="-">Subtração</option>
                <option value="*">Multiplicação</option>
                <option value="/">Divisão</option>
                </select>
            </div>
            <div class="col-md-8">
                <input v-model.number="props.estado.num1" type="number" class="form-control mb-3 text-center w-100" placeholder="Digite um número">
            </div>
            <div class="col-md-8">
                <input v-model.number="props.estado.num2" type="number" class="form-control mb-3 text-center w-100" placeholder="Digite um número">
            </div>
        </div>
    </form>
</template>

<style scoped>
</style>