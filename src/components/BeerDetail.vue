<template lang="html">
  <div v-if="beer">
    <p>{{ beer.name }}</p>
    <p>{{ beer.abv }}</p>
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
