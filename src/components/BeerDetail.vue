<template lang="html">
  <div id="detailWrapper">
    <div v-if="beer">
      <ul class="detailData">
        <h4>Name: {{ beer.name }}</h4>
        <div>
          <img :src="beer.image_url" :alt="beer.name">
        </div>
        <h5>ABV: {{ beer.abv }}</h5>
        <p>Description: {{beer.description}}</p>
      </ul>
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
  height: 250px;
}
#detailWrapper {
/* display: flex; */
flex-direction: row;
box-sizing: border-box;
border: 1px solid black;
border-radius: 10px;
background: #cbc8b9;
padding: 10px;
height: 500px;
font-family: sans-serif;

}

.detailData {
  width: 60%;
  /* font-family: 'Arizonia'; */

}
</style>
