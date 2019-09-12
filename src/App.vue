<template lang="html">
  <div>
    <h1>BrewDog Beers</h1>
    <beer-dropdown :beers="beers"></beer-dropdown>
    <beer-detail :beer="selectedBeer"></beer-detail>
  </div>
</template>

<script>

import BeersDropDown from './components/BeersDropDown.vue'
import BeerDetail from './components/BeerDetail.vue'
import { eventBus } from './main.js'

export default {
  data(){
    return {
      beers: [],
      selectedBeer: null
    }
  },
  mounted(){
    fetch('https://api.punkapi.com/v2/beers')
    .then(res => res.json())
    .then(beers => this.beers = beers)

    eventBus.$on('beer-selected', (beer) => {
      this.selectedBeer = beer
    })
  },
  components: {
    "beer-dropdown": BeersDropDown,
    "beer-detail": BeerDetail
  }
}
</script>

<style lang="css" scoped>
</style>
