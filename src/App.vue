  <!-- Criar um projeto utilizando VueJS;

• Este projeto será uma calculadora aritmética;

• Deverá conter dois campos para inserir os números;

• Um campo do tipo select para escolher a operação aritmética;

• Ao alterar os valores o cálculo já deverá ser realizado, sem precisar clicar em nenhum botão;

• Crie um repositório no Github para esta tarefa e nos envie o link pela plataforma.  -->

<script setup>

</script>

<template>
  <form >
    <div class="row">
      <div class="col">
        <h1>Calculadora Aritmética</h1>
        <input ype="number" /> 
        <input  type="number" />
      </div>
      <div class="col">
        <p>Selecione uma operação</p>
        <select>
        <option value="">Selecione uma opção</option>
          <option value="somar">Somar</option>
          <option value="dividir">Dividir</option>
          <option value="subtrair">Subtrair</option>
          <option value="multiplicar">Multiplicar</option>
        </select>
      </div>
      <div class="col">
        <p>O resultado é: {{ estado.resultado }} </p>
      </div>
    </div>
  </form>
</template>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
