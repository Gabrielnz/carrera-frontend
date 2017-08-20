<template>
  <div>
    <Header v-on:activeCanvas='activeCanvas' v-on:inactiveCanvas='inactiveCanvas'/>
    <div class='mainContainer' :class='{lowBrightness}'>
      <slot></slot>
    </div>
    <Footer :class='{lowBrightness}'/>
  </div>
</template>

<script>

import Header from '../Header/Main.vue'
import Footer from '../Footer/Main.vue'

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
    Header,
    Footer
  }
}

</script>

<style lang='scss' scoped>

@import '../../App.scss';

.mainContainer {
  padding-top: $vertical-space;
  height: 1000px;
  background-color: white;
  transition: 0.3s;
}

.lowBrightness { filter: brightness(75%); }

@include media-breakpoint-sm {

  .mainContainer { padding-top: 7.5em + $vertical-space-sm; }
}

</style>
