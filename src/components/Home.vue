<template>
  <div>
    <RaceHeader/>
    <div>Cuerpo :DDD</div>
    <RaceFooter/>
  </div>
</template>

<script>

import RaceHeader from './Header/Main.vue'
import RaceFooter from './Footer.vue'

export default {
  name: 'race-home',
  data () {
    return {
      navigation: true
    }
  },
  components: {
    RaceHeader,
    RaceFooter
  }
}

</script>

<style lang='scss' scoped>

@import '../App.scss';

</style>
