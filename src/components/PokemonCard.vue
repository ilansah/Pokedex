<script setup>
const props = defineProps({
  pokemon: {
    type: Object,
    required: true
  }
})

const emit = defineEmits(['select'])

const handleClick = () => {
  emit('select', props.pokemon)
}
</script>

<template>
  <div class="card" :class="pokemon.type" @click="handleClick">
    <img :src="pokemon.img" :alt="pokemon.name">
    <h2>{{ pokemon.name }}</h2>
    <br>
    <p>#{{ pokemon.number }}</p>
    <div class="type">
      <p>{{ pokemon.type }}</p>
    </div>
    <button class="favori" @click.stop="alert('Ajouté aux favoris !')">Favori</button>
  </div>
</template>

<style scoped>
.card {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    border-radius: 20px;
    padding: 30px;
    border: 3px solid transparent;
    background-clip: padding-box;
    cursor: pointer;
    transition: transform 0.2s;
    min-width: 200px;
}

.card:hover {
    transform: scale(1.05);
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
    color: black;
    margin: 5px 0;
    font-weight: 500;
}

.card.Électrique {
    background-color: #fffacd;
}

.card.Plante {
    background-color: #d4f4dd;
}

.card.Feu {
    background-color: #ffd4d4;
}

.card.Eau {
    background-color: #d4e8ff;
}

.card.Normal {
    background-color: #f0f0f0;
}

.card.Électrique .type p {
    background-color: #ffd700;
    padding: 5px 15px;
    border-radius: 15px;
}

.card.Plante .type p {
    background-color: #90ee90;
    padding: 5px 15px;
    border-radius: 15px;
}

.card.Feu .type p {
    background-color: #ff6b6b;
    padding: 5px 15px;
    border-radius: 15px;
}

.card.Eau .type p {
    background-color: #6bb6ff;
    padding: 5px 15px;
    border-radius: 15px;
}

.card.Normal .type p {
    background-color: #c0c0c0;
    padding: 5px 15px;
    border-radius: 15px;
}

.favori {
    margin-top: 15px;
    padding: 8px 16px;
    font-size: 14px;
    color: white;
    background: #667eea;
    border: none;
    border-radius: 8px;
    cursor: pointer;
}

.favori:hover {
    background: #764ba2;
}

</style>
