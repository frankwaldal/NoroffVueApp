<template>
  <div>
    <h1>Recipes</h1>
    <div class="recipes">
      <div :key="recipe.title" v-for="recipe in recipes">
        <RecipeComponent
          v-bind:title="recipe.title"
          v-bind:details="recipe.href"
          v-bind:image="recipe.thumbnail"
          v-bind:ingredients="recipe.ingredients"
          />
      </div>
    </div>
  </div>
</template>

<script>
import sortBy from 'lodash/sortBy'

import RecipeComponent from './components/RecipeComponent.vue'

export default {
  name: 'RecipePage',
  components: {
    RecipeComponent
  },
  data() {
    return {
      recipes: []
    }
  },
  beforeMount() {
    const PROXY_URL = 'https://cors-anywhere.herokuapp.com/';
    const API_URL = 'http://www.recipepuppy.com/api/';
    fetch(PROXY_URL+API_URL)
      .then(resolve => {
        resolve.json().then(data => {
          this.recipes = sortBy(data.results, 'title');
        })
      })
  }
}
</script>

<style scoped>
h1 {
  text-align: center;
}
.recipes {
  display: grid;
  grid-template-columns: repeat(3, minmax(0,1fr));
  grid-row-gap: 0.75rem;
  grid-column-gap: 0.75rem;
}
</style>
