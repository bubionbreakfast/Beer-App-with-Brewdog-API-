<template lang="html">
  <div>
    <h2>Your Favorite Beers:</h2>
    <li v-for="beer in favBeers" value="beer">{{beer.name}} <img :src="beer.image_url" :alt="beer.name"></li>

  </div>
</template>

<script>

import { eventBus } from '../main.js'

export default {
  name: 'fav-list',
  props: ['favBeers']

}
</script>

<style lang="css" scoped>
img {
  height: 50px;
}
</style>
