<script setup lang="ts">
import type { iDrink } from "@/models/drink";

import { defineEmits } from "vue";

interface DrinkProps {
  drink: iDrink;
}

defineProps<DrinkProps>()

defineEmits<{
  (strDrink: string): void;
}>();
</script>

<template>
  <div class="drink-div">
  <h2>{{ drink.strDrink }}</h2>
  <p>Id: {{ drink.idDrink }}</p>
  <div id="ingredients">
  <h3>Ingredients: </h3>
    <p>{{ drink.strIngredient1 }}</p>
    <p>{{ drink.strIngredient2 }}</p>
    <p>{{ drink.strIngredient3 }}</p>
    <p>{{ drink.strIngredient4 }}</p>
    <p>{{ drink.strIngredient5 }}</p>
    <p>{{ drink.strIngredient6 }}</p>
    <p>{{ drink.strIngredient7 }}</p>
  </div>
  <h4>Instructions: </h4>
  <p>{{ drink.strInstructions }}</p>
  <img :src="drink.strDrinkThumb" alt="Bild på drycken">
  </div>
</template>

<style scoped>
.drink-div {
  margin: 10px;
  padding: 10px;
  display: flex;
  flex-direction: column;
  border: black solid 1px;
}
img {
  width:20%;
}
</style>