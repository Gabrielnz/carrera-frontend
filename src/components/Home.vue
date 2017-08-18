<template>
  <div>
    <RaceHeader/>
    <div>Cuerpo :DDD</div>
    <RaceFooter/>
  </div>
</template>

<script>

import RaceHeader from './Header.vue'
import RaceFooter from './Footer.vue'

export default {
  name: 'race-home',
  components: {
    RaceHeader,
    RaceFooter
  }
}

</script>

<style scoped>

</style>
