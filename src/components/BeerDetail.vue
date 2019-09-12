<template lang="html">
  <div v-if="beer">
    <ul>
      <li>Name: {{ beer.name }}</li>
      <li>ABV: {{ beer.abv }}</li>
      <li>Description: {{beer.description}}</li>
    </ul>
    <img :src="beer.image_url" :alt="beer.name">
  </div>
</template>

<script>

import { eventBus } from '../main.js'

export default {
  name: "beer-detail",
  props: ['beer']
}
</script>

<style lang="css" scoped>
</style>
