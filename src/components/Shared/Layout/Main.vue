<template>
  <div>
    <RaceHeader v-on:activeCanvas='activeCanvas' v-on:inactiveCanvas='inactiveCanvas' />
    <div class='mainContainer' :class='{lowBrightness}'>
      <div class='container-fluid'>
        <slot></slot>
      </div>
    </div>
    <RaceFooter :class='{lowBrightness}' />
  </div>
</template>

<script>

import RaceHeader from '../Header/Main.vue'
import RaceFooter from '../Footer/Main.vue'

export default {
  name: 'layout',
  data: function () {
    return {
      lowBrightness: false
    }
  },
  methods: {
    activeCanvas: function (ev) { this.lowBrightness = true },
    inactiveCanvas: function (ev) { this.lowBrightness = false }
  },
  components: {
    RaceHeader,
    RaceFooter
  }
}

</script>

<style lang='scss' scoped>

@import './Theme.scss';

.mainContainer {
  padding-top: $vertical-space;
  height: 1000px;
  background-color: white;
  transition: 0.3s;
  background-image: url('./assets/main-section-bg.png');
  background-size: 100%;
}

.lowBrightness { filter: brightness(75%); }

@include media-breakpoint-sm {

  .mainContainer {
    padding-top: 7.5em + $vertical-space-sm;
    background-image: initial;
  }
}

</style>
