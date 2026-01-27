<script setup>
const search = defineModel()
</script>

<template>
  <div class="search-container">
    <input 
      type="text" 
      v-model="search" 
      placeholder="Rechercher un Pokémon..."
      class="search-input"
    >
  </div>
</template>

<style scoped>
.search-container {
  margin-bottom: 20px;
  width: 100%;
  max-width: 400px;
}

.search-input {
  width: 100%;
  padding: 10px;
  font-size: 16px;
  border: 1px solid #ccc;
  border-radius: 5px;
  outline: none;
}

.search-input:focus {
  border-color: #4ade80;
}
</style>
