<template lang="html">
  <div>
    <button v-on:click="handleClick">Add to Fav's</button>

    <ul >
    </ul>
  </div>
</template>

<script>

import { eventBus } from '../main.js'

export default {
  name: 'beer-fav',

  props: ['beer'],
  methods: {
    handleClick(){
      eventBus.$emit('fav-list', this.beer)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
