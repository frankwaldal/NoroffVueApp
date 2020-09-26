<template>
  <div id="app">
    <RecipePage />
  </div>
</template>

<script>
import RecipePage from './RecipePage.vue'

export default {
  name: 'App',
  components: {
    RecipePage
  }
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
}
#app {
  margin: 20px;
}
</style>
