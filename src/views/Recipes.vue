<template>
  <div class="container-xl">
    <div class="text-center">
        <h1>Formulación de recetas</h1>
    </div>
    <div class="row">
        <div class="col-lg-12 col-md-8">
            <div v-for="fruit in fruits" :key="fruit.id">
                <p>Fruta: </p>
                <h3>{{fruit.name}}</h3>
                <p>Azúcar: {{fruit.sugar}} °BRIX</p>
                <p>Acidez inicial: {{fruit.acidity}} g/L</p>
                <p>Límite de agua: {{fruit.waterLimit * 100}}%</p>
                <hr>
                <h2>Datos a llenar:</h2>
                <h4>Peso de pulpa:</h4>
                <h3>{{pulp}} Kg</h3>
                <p>{{fruitWaterLimit}}</p>
            </div>
        </div>
    </div>
  </div>
</template>

<script>

import {ref} from 'vue'
import fruits from '../components/data/fruitsDB.json'

export default {
    setup() {
        fruits;
        var pulp = ref(1);

        return {
            pulp,
            fruits,
        }
    }
}
</script>

<style>

</style>