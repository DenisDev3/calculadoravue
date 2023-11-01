<script setup>
const props = defineProps(['Calculadora','filtro','mais','menos','dividir','multiplicar']);
</script>
<template>
    <div class="row">
        <div class="col-md-2">
            <select v-model="props.Calculadora.filtro" class="form-select">
                <option value="multiplicar">Multiplicar</option>
                <option value="dividir">Divisão</option>
                <option value="menos">Subtração</option>
                <option value="mais">Adição</option>
            </select>
            <input type="number" v-model="Calculadora.campoA" placeholder="Digite um número" class="form-control">
            <input type="number" v-model="Calculadora.campoB" placeholder="Digite um número" class="form-control">

            <p>Resultado: {{  props.filtro }}</p>
        </div>
    </div>
</template>
<style scoped>
p{
    color: white;
}
</style>