<script setup>
import { onMounted, reactive, ref } from "vue"
import ListPokemons from "../components/ListPokemons.vue";

let pokemons = reactive(ref());
let urlBaseSvg = ref("https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/")

onMounted(()=>{
  fetch("https://pokeapi.co/api/v2/pokemon?limit=251&offset=0")
  .then(res => res.json())
  .then(res =>{
    pokemons = res.results
    console.log(pokemons);
  });
})

</script>

<template>
<main>
  <div class="container">
    <div class="row mt-4">
      <div class="col-sm-12 col-md-6">
      </div>
        <div class="card">
          <div class="card-body row" style>
          <ListPokemons 
          v-for="pokemon in pokemons"
          :key="pokemon.name"
          :name="pokemon.name"
          :urlBaseSvg="urlBaseSvg + pokemon.url.split('/')[6]+'.svg'"
          />
          </div>
          </div>
          </div>
          </div>
        
  </main>
</template>
