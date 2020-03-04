<template>
  <article class="recipe">
    <h2>
      <a class="recipe-link" v-bind:href="url">{{title}}</a>
      <img class="recipe-thumbnail" v-bind:src="thumbnail" />
      <ul class="ingredients">
        <li v-for="(ingredient, index) in ingredients" :key="index" v-text="ingredient" />
      </ul>
    </h2>
  </article>
</template>

<script>
export default {
  name: "Recipe",
  props: {
    title: String,
    tooltip: String,
    url: String,
    ingredients: Array,
    thumbnail: String
  }
};
</script>

<style>
.recipe {
  display: flex;
  flex-flow: column;
  width: 280px;
}

.ingredients {
  text-align: left;
}

.recipe-thumbnail {
  width: 120px;
  height: auto;
}

.recipe-link {
  display: block;
  color: #42b983;
  text-decoration: none;
  margin-bottom: 8px;
}
</style>
