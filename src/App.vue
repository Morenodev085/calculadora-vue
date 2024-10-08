<template>
  <div class="container mt-5">
    <div class="row">
      <h1 class="text-center mb-4">Calculadora Aritmética</h1>
      <div class="col-md-4">
        <h3>Primeiro Número</h3>
        <input type="number" v-model="num1" placeholder="Primeiro Número" class="form-control" />
      </div>
      <div class="col-md-4">
        <h3>Escolha a operação</h3>
        <select class="form-control" v-model="operacao">
          <option value="+">+</option>
          <option value="-">-</option>
          <option value="*">x</option>
          <option value="%">%</option>
        </select>
      </div>
      <div class="col-md-4">
        <h3>Segundo Número</h3>
        <input type="number" v-model="num2" placeholder="Segundo Número" class="form-control" />
      </div>
    </div>
    <div class="row mt-4">
      <div class="col text-center">
        <h2>Resultado: {{ resultado }}</h2>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operacao: '+',
    };
  },
  computed: {
    resultado() {
      switch (this.operacao) {
        case '+':
          return this.num1 + this.num2;
        case '-':
          return this.num1 - this.num2;
        case '*':
          return this.num1 * this.num2;
        case '%':
          return (this.num1 * this.num2) / 100;
        default:
          return 0;
      }
    },
  },
};
</script>

<style scoped>
.container {
  max-width: 600px;
  margin: auto;
}
</style>
