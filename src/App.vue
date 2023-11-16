<template>
    <div class="calculadora">

    <h1>Calculadora Aritmética Vuejs</h1>

    <div>
      <label for="num1">Número 1:</label>
      <input v-model="num1" type="number" id="num1" @input="calcula" />
    </div>

    <div>
      <label for="operador">Operação:</label>
      <select v-model="operador" id="operador" @change="calcula">
        <option value="+">Soma</option>
        <option value="-">Subtração</option>
        <option value="*">Multiplicação</option>
        <option value="/">Divisão</option>
      </select>
    </div>

    <div>
      <label for="num2">Número 2:</label>
      <input v-model="num2" type="number" id="num2" @input="calcula" />
    </div>

    <div>
      <label for="resultado">Resultado:</label>
      <input v-model="resultado" type="number" id="resultado" readonly />
    </div>
  </div>

</template>

  <script>

  export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operador: '+',
      resultado: 0
    };
  },
  methods: {
    calcula() {
      switch (this.operador) {
        case '+':
          this.resultado = parseFloat(this.num1) + parseFloat(this.num2);
          break;
        case '-':
          this.resultado = parseFloat(this.num1) - parseFloat(this.num2);
          break;
        case '*':
          this.resultado = parseFloat(this.num1) * parseFloat(this.num2);
          break;
        case '/':
          this.resultado = parseFloat(this.num1) / parseFloat(this.num2);
          break;
        default:
          this.resultado = 0;
      }
    }
  }
}
  </script>

<style scoped>
.calculadora {
  max-width: 400px;
  margin: auto;
  padding: 20px;
  border: 1px solid #ccc;
  background-color: rgb(101, 101, 230);
  border-radius: 5px;
}

div {
  margin-bottom: 10px;
}
</style>