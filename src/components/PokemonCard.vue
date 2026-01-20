<script setup>
import { ref } from 'vue'

const pokemons = ref([
  {
    id: 1,
    img: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/25.png",
    name: "Pikachu",
    number: 25,
    type: "Électrique"
  },
  {
    id: 2,
    img: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/1.png",
    name: "Bulbizarre",
    number: 1,
    type: "Plante"
  },
  {
    id: 3,
    img: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/4.png",
    name: "Salamèche",
    number: 4,
    type: "Feu"
  },
  {
    id: 4,
    img: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/7.png",
    name: "Carapuce",
    number: 7,
    type: "Eau"
  },
  {
    id: 5,
    img: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/39.png",
    name: "Rondoudou",
    number: 39,
    type: "Normal"
  }
  
])
</script>

<template>
<div class="pokemon-container">
  <div class="card" v-for="pokemon in pokemons" :key="pokemon.id">
    <img :src="pokemon.img" :alt="pokemon.name">
    <h2>{{ pokemon.name }}</h2>
    <br>
    <p>#{{ pokemon.number }}</p>
    <p>{{ pokemon.type }}</p>
  </div>
</div>
</template>

<style scoped>
.pokemon-container {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 20px;
    padding: 0 20px;
}

.card {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    background-color: #f0f0f0;
    border-radius: 20px;
    padding: 30px 30px;
    border: 3px solid transparent;
    background-clip: padding-box;
}

img {
    width: 150px;
    height: 150px;
    margin-bottom: 15px;
}

h2 {
    font-size: 28px;
    font-weight: 700;
    color: #2d3748;
    margin: 10px 0;
    letter-spacing: 0.5px;
}

p {
    font-size: 16px;
    color: #4a5568;
    margin: 5px 0;
    font-weight: 500;
}

p:first-of-type {
    color: #718096;
    font-weight: 600;
    font-size: 14px;
}

p:last-of-type {
    background: linear-gradient(135deg, #667eea, #764ba2);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    font-weight: 700;
    font-size: 18px;
    margin-top: 10px;
}
</style>
