<script setup>
import PokemonCard from './components/PokemonCard.vue'
</script>

<template>
  <div class="app">
    <header>
      <h1>Mon Pokédex</h1>
    </header>
    <PokemonCard />
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
</style>
