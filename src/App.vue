<script setup>
import { ref, computed } from 'vue'
import PokemonCard from './components/PokemonCard.vue'
import SearchInput from './components/SearchInput.vue'

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

const selectedPokemon = ref(null)
const search = ref('')

const filteredPokemons = computed(() => {
  if (!search.value) return pokemons.value
  return pokemons.value.filter(pokemon => 
    pokemon.name.toLowerCase().includes(search.value.toLowerCase())
  )
})

const handleSelect = (pokemon) => {
  selectedPokemon.value = pokemon
}
</script>

<template>
  <div class="app">
    <header>
      <h1>Mon Pokédex</h1>
      <p v-if="selectedPokemon" class="selection-message">
        Vous avez sélectionné : {{ selectedPokemon.name }}
      </p>
    </header>
    
    <SearchInput v-model="search" />
    
    <div class="pokemon-container">
      <PokemonCard
        v-for="pokemon in filteredPokemons" 
        :key="pokemon.id" 
        :pokemon="pokemon"
        @select="handleSelect"
      />
    </div>
  </div>
</template>

<style>
body {
  margin: 0;
  padding: 0;
  min-height: 100vh;
}

.app {
  padding: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  margin: 0 auto;
}

header {
  text-align: center;
  margin-bottom: 30px;
}

header h1 {
  color: white;
  font-size: 48px;
  margin: 0;
  font-weight: 700;
}

.selection-message {
  color: #4ade80;
  font-size: 24px;
  font-weight: 600;
  margin-top: 15px;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
}

.pokemon-container {
  display: grid;
  grid-template-columns: repeat(4, auto);
  gap: 20px;
  justify-content: center;
  width: 100%;
}
</style>
