<script setup>

import { reactive } from 'vue';

const estado = reactive({
    numero1: 0,
    numero2: 0,
    operacao: 'somar',
    resultado: 0,

});

 
 const calcularResultado = () => {
      switch (estado.operacao) {
        case 'somar':
          estado.resultado = parseFloat(estado.numero1) + parseFloat(estado.numero2);
          break;
        case 'subtrair':
          estado.resultado = parseFloat(estado.numero1) - parseFloat(estado.numero2);
          break;
        case 'dividir':
          estado.resultado = parseFloat(estado.numero1) / parseFloat(estado.numero2);
          break;
        case 'multiplicar':
          estado.resultado = parseFloat(estado.numero1) * parseFloat(estado.numero2);
          break;
        default:
          break;
      }
 }
</script>

<template>
     <form class="bg-light p-4">
      <div class="row">
        <div class="col">
          <input v-model="estado.numero1" class="mb-5" type="number" @keyup="calcularResultado()" @change="calcularResultado()" />
          <input v-model="estado.numero2" type="number"  @keyup="calcularResultado()" @change="calcularResultado()" />
        </div>
        <div class="col">
          <p>Selecione uma operação</p>
          <select v-model="estado.operacao" class="form-control" @change="calcularResultado()">
            <option value="somar">Somar</option>
            <option value="dividir">Dividir</option>
            <option value="subtrair">Subtrair</option>
            <option value="multiplicar">Multiplicar</option>
          </select>
        </div>
        <div class="col">
          <p>O resultado é: <span class="fs-4">{{ estado.resultado }}</span></p>
        </div>
      </div>
    </form>
</template>