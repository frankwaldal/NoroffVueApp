<template>
  <div class="recipe">
    <img :src="image" />
    <div>
      <h3>{{ title }}</h3>
      <p>Ingredients: {{ ingredients }}</p>
      <p><a :href="details" target="_blank" rel="noopener noreferrer">Detailed description</a></p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'RecipeComponent',
  props: ['details', 'image', 'ingredients', 'title']
}
</script>

<style scoped>
.recipe {
  background: #f6f0fa;
  border-radius: 1rem;
  padding: 0.5rem;
  display: grid;
  grid-template-columns: max-content auto;
  grid-column-gap: 1rem;
}
.recipe img {
  align-self: center;
}
</style>
