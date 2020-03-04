<template>
  <div id="app">
    <Recipes v-bind:recipes="recipes" />
  </div>
</template>

<script>
import axios from "axios";
import Recipes from "./components/Recipes.vue";

export default {
  name: "App",
  data() {
    return {
      recipes: null
    };
  },
  components: {
    Recipes
  },
  methods: {
    getRecipes() {
      axios
        .get(
          "https://cors-anywhere.herokuapp.com/http://www.recipepuppy.com/api"
        )
        .then(response => {
          this.recipes = response.data.results;
        });
    }
  },
  mounted() {
    this.getRecipes();
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
