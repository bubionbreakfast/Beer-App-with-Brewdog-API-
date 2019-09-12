<template lang="html">
  <div v-if="beer">
    <ul>
      <li>Name: {{ beer.name }}</li>
      <li>ABV: {{ beer.abv }}</li>
      <li>Description: {{beer.description}}</li>
    </ul>
    <!-- <button v-on:click="handleClick">Add to Fav's</button> -->
    <img :src="beer.image_url" :alt="beer.name">
    <beer-fav :beer="beer"></beer-fav>

  </div>
</template>

<script>
import AddToFavouritesButton from './AddToFavouritesButton.vue'
import { eventBus } from '../main.js'

export default {
  name: "beer-detail",
  props: ['beer'],
  components: {
    "beer-fav": AddToFavouritesButton
  }


}
</script>

<style lang="css" scoped>
</style>
