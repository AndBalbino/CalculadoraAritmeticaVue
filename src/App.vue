<script>
export default {
  name: "App",
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: 'somar',
      resultado: 0,
    };
  },

  watch: {
    operacao: 'calcularResultado',
  },
  methods: {
    calcularResultado() {
      switch (this.operacao) {
        case 'somar':
          this.resultado = parseFloat(this.numero1) + parseFloat(this.numero2);
          break;
        case 'subtrair':
          this.resultado = parseFloat(this.numero1) - parseFloat(this.numero2);
          break;
        case 'dividir':
          this.resultado = parseFloat(this.numero1) / parseFloat(this.numero2);
          break;
        case 'multiplicar':
          this.resultado = parseFloat(this.numero1) * parseFloat(this.numero2);
          break;
        default:
          break;
      }
    },
  }
}
</script>

<template>
  <div class="container">
    <header class="p-5 mb-4 mt-4 bg-light rounded-3">
      <h1>Calculadora Aritmética</h1>
    </header>
    <form class="bg-light p-4">
      <div class="row">
        <div class="col">
          <input v-model="numero1" class="mb-5" type="number" />
          <input v-model="numero2" type="number" />
        </div>
        <div class="col">
          <p>Selecione uma operação</p>
          <select v-model="operacao" class="form-control">
            <option value="somar">Somar</option>
            <option value="dividir">Dividir</option>
            <option value="subtrair">Subtrair</option>
            <option value="multiplicar">Multiplicar</option>
          </select>
        </div>
        <div class="col">
          <p>O resultado é: <span class="fs-4">{{ resultado }}</span></p>
        </div>
      </div>
    </form>
  </div>
</template>

<style scoped></style>