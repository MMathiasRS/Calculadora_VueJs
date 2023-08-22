<template>
  <div class="calculator">
    <h1>Calculadora Aritmética</h1>
    <div class="input-section">
      <label for="number1">Número 1:</label>
      <input type="number" id="number1" v-model="number1" @input="calculate">
      
      <label for="number2">Número 2:</label>
      <input type="number" id="number2" v-model="number2" @input="calculate">
      
      <label for="operation">Operação:</label>
      <select id="operation" v-model="operation" @change="calculate">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">*</option>
        <option value="divide">/</option>
      </select>
    </div>
    <div class="result">
      Resultado: {{ result }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: 'add',
      result: 0
    };
  },
  methods: {
    calculate() {
      switch (this.operation) {
        case 'add':
          this.result = this.number1 + this.number2;
          break;
        case 'subtract':
          this.result = this.number1 - this.number2;
          break;
        case 'multiply':
          this.result = this.number1 * this.number2;
          break;
        case 'divide':
          this.result = this.number1 / this.number2;
          break;
      }
    }
  },
  created() {
    this.calculate();
  }
};
</script>

<style scoped>
.calculator {
  text-align: center;
  margin-top: 30px;
}
.input-section {
  margin-bottom: 20px;
}
</style>