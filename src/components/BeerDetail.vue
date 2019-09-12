<template lang="html">
  <div id="detailWrapper">
    <div v-if="beer">
      <ul class="detailData">
        <li>Name: {{ beer.name }}</li>
        <li>ABV: {{ beer.abv }}</li>
        <li>Description: {{beer.description}}</li>
      </ul>
      <div>
        <img :src="beer.image_url" :alt="beer.name">
      </div>

      <beer-fav :beer="beer"></beer-fav>

    </div>
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
img {
  height: 300px;
}
#detailWrapper {
/* display: flex; */
flex-direction: row;
box-sizing: border-box;
background: #cbc8b9;
padding: 10px;
height: 500px;

}

.detailData {
  width: 60%;
}
</style>
