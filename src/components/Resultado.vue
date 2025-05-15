<script setup>
import { defineProps } from 'vue';

defineProps(['resultado']);
</script>

<template>
    <div class="mt-4 text-center">
        <h3>Resultado: {{ resultado }}</h3>
    </div>
</template>

<style scoped>
</style>