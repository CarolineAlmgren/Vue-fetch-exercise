<script setup lang ="ts">
import { onMounted, ref } from 'vue';
import type {iDrink} from '@/models/drink';
import Drink from './Drink.vue';
import type { drinkResponse } from '@/models/drinkresponse';

const drinks = ref<iDrink[]>([])

onMounted(async ()=>{
  const response = await fetch("https://www.thecocktaildb.com/api/json/v1/1/search.php?s=gin")
  if(!response.ok){
  }
  const data: drinkResponse = await response.json()
  drinks.value = data.drinks
})

</script>

<template>
<h1>My drinks</h1>
    <Drink v-for="drink in drinks" :key="drink.strDrink" :drink="drink"  />
  
</template>

<style scoped>

</style>