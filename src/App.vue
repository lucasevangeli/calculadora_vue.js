<script setup>
import { ref } from 'vue';

const numero1 = ref(0);
const numero2 = ref(0);
const operacao = ref('+');
const resultado = ref(0);

const calcular = () => {
  switch (operacao.value) {
    case '+':
      resultado.value = numero1.value + numero2.value;
      break;
    case '-':
      resultado.value = numero1.value - numero2.value;
      break;
    case '*':
      resultado.value = numero1.value * numero2.value;
      break;
    case '/':
      resultado.value = numero1.value / numero2.value;
      break;
    default:
      resultado.value = 0;
  }
};
</script>

<template>
  <header class="container">
    <div id="app" class="container mt-5">
      <h1 class="mb-4">Calculadora Aritmética Vue</h1>

      <div class="form-group">
        <label for="numero1">Número 1:</label>
        <input required v-model="numero1" type="number" class="form-control" @input="calcular">
      </div>

      <div class="form-group">
        <label for="numero2">Número 2:</label>
        <input v-model="numero2" type="number" class="form-control" @input="calcular">
      </div>

      <div class="form-group">
        <label for="operacao">Operação:</label>
        <select v-model="operacao" class="form-control" @change="calcular">
          <option value="+">Soma (+)</option>
          <option value="-">Subtração (-)</option>
          <option value="*">Multiplicação (*)</option>
          <option value="/">Divisão (/)</option>
        </select>
      </div>

      <div class="form-group">
        <label for="resultado">Resultado:</label>
        <input :value="resultado" type="text" class="form-control" readonly>
      </div>
    </div>
  </header>
</template>

<style scoped>
  #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #ffffff;
  margin-top: 60px;
}

.form-group {
  margin-bottom: 20px;
}

h1 {
  font-size: 2em;
  margin-bottom: 20px;
}

.container {
  text-align: start;
  padding: 40px;
  border-radius: 30px;
  max-width: 400px;
  margin: 0 auto;
  background-color: black;
}
</style>
