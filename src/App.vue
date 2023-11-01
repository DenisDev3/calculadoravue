<script setup>
import { reactive, ref } from 'vue';
import Calculista from './components/Calculista.vue' ;

// ----------------------------------------------------------------:

const Calculadora = reactive({
  campoA: 0,
  campoB: 0,
  filtro: ref('multiplicar','dividir','menos','mais'), // Defina o filtro padrão aqui
});

const mais = () => {
    return Calculadora.campoA + Calculadora.campoB;
  }

const menos = () => {
  return Calculadora.campoA - Calculadora.campoB;
}

const dividir = () => {
  return Calculadora.campoA / Calculadora.campoB;
}

const multiplicar = () => {
  return Calculadora.campoA * Calculadora.campoB;
}

const getFiltroCalculo = () => {
  switch (Calculadora.filtro) {
    case 'multiplicar':
      return multiplicar();
    case 'dividir':
      return dividir();
    case 'menos':
      return menos();
    case 'mais':
      return mais();
    default:
      return multiplicar();
  }
}
</script>

<template>
  <div class="container row">
    <Calculista class="col-md-12" :filtro="getFiltroCalculo()" :-calculadora="Calculadora" :dividir="dividir()" :mais="mais()" :multiplicar="multiplicar()" :menos="menos()"  />
  </div>
</template>
<style scoped>
img {
  width: 250px;
  height: 260px;
}
.container{
  background-image: url(./images/OIG.jpeg);
}
</style>
