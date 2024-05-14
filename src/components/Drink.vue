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
  <h3>{{ drink.strDrink }}</h3>
  <p>Id: {{ drink.idDrink }}</p>
  <div id="ingredients">
  <h4>Ingredients: </h4>
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
  display: flex;
  flex-direction: column;
}
img {
  width:20%;
}
</style>