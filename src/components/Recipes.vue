<template>
  <section>
    <Recipe
      v-for="(recipe, index) in recipes"
      v-bind:key="index"
      v-bind:title="recipe.title"
      v-bind:tooltip="`Go to ${recipe.title} page.`"
      v-bind:url="recipe.href"
      v-bind:ingredients="recipe.ingredients.split(',')"
      v-bind:thumbnail="recipe.thumbnail"
    />
  </section>
</template>

<script>
import Recipe from "./Recipe";
export default {
  name: "Recipes",
  props: {
    recipes: Array
  },
  components: { Recipe }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
section {
  display: flex;
  flex-flow: column;
  align-items: center;
}
</style>
