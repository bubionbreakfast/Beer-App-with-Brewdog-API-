<template lang="html">
  <form v-on:submit.prevent>
    <select v-on:change="handleSelect" v-model="selectedBeer">
      <option disabled value="">Select A Beer</option>
      <option v-for="beer in beers" :value="beer">{{ beer.name }}</option>
    </select>
  </form>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: "beer-dropdown",
  data(){
    return {
      selectedBeer: {}
    }
  },
  props: ["beers"],
  methods: {
    handleSelect(){
      eventBus.$emit('beer-selected', this.selectedBeer)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
