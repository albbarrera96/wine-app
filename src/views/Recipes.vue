<template>
  <div class="container-xl">
    <div class="text-center">
        <h1>Formulación de recetas</h1>
    </div>
    <div class="row">
        <div class="col-lg-12 col-md-8">
            <div class="form-floating">
                <select class="form-select" id="floatingSelect" aria-label="Floating label select example" v-model="selectedFruit">
                    <option v-for="fruit in fruits" :key="fruit.id" :value="fruit">{{fruit.name}}</option>
                </select>
                <label for="floatingSelect">Escoja una fruta</label>
            </div>
            <button class="btn btn-dark mt-2" @click="getFruitData">Click Here</button>
            <hr>
            <h4>Id de la fruta: {{selectedFruit.id}}</h4>
            <h4>Nombre de la fruta: {{selectedFruit.name}}</h4>
            <h4>Azúcar inicial: {{selectedFruit.sugar}}</h4>
            <h4>Acidez de la fruta: {{selectedFruit.acidity}}</h4>
            <h4>Límite de agua: {{selectedFruit.waterLimit * 100}}%</h4>
            <p>{{addWater}}</p>
        </div>
    </div>
  </div>
</template>

<script>

import {computed, ref} from 'vue'
import fruits from '../components/data/fruitsDB.json'

export default {
    setup() {
        fruits;
        var pulp = ref(2);
        var selectedFruit = ref([]);
        const getFruitData = computed (() => {
            console.log(selectedFruit)
        });

        return {
            pulp,
            fruits,
            selectedFruit,
            getFruitData,
            
        }
    }
}
</script>

<style>

</style>