<template>
<div>
  <header class='d-flex align-items-center'>
    <div class='container-fluid'>
      <div class='row align-items-center justify-content-end no-gutters'>
        <button id='offCanvasButton' class='d-flex align-items-center justify-content-center' v-if='showOffCanvas' @click='toggleOffCanvas'>
          <i class="fa fa-bars" aria-hidden="true"></i>
        </button>
        <div class='col-2 col-md-4 d-flex align-items-center justify-content-center'>
          <a href='#'>
            <img id='raceLogo' src='/static/assets/logo.png'>
          </a>
        </div>
        <div class='col-md-4 d-none d-md-flex align-items-center justify-content-center'>
          <img id='headerLogo' src='./assets/header-logo.png'>
        </div>
        <div class='col-8 col-md-4 d-flex align-items-center justify-content-center'>
          <div id='registerContainer' class='d-flex flex-row-reverse justify-content-around flex-md-column align-items-center justify-md-content-center'>
            <a id='registerLink' class='d-flex align-items-center justify-content-center' href='#'><span>Regístrate <br> como Corredor</span></a>
            <div id='collectedBanner' class='d-flex flex-column align-items-center justify-content-center'>
              <span>Monto Recaudado</span>
              <span>$1,907,632 MXN</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </header>
  <Navigation v-if='showNavigation' :links='links' />
  <OffCanvas v-if='showOffCanvas' :active='activeCanvas' :links='links' />
</div>
</template>

<script>
import Navigation from './Navigation.vue'
import OffCanvas from './OffCanvas.vue'

export default {
  name: 'header',
  data: function () {
    return {
      smallScreen: false,
      offCanvas: false,
      activeCanvas: false,
      mediaQuery: window.matchMedia('(max-width: 767px)'),
      links:
      [
        { id: 'link1', url: '/', name: 'Home' },
        { id: 'link2', url: '#', name: 'Corredores' },
        { id: 'link3', url: '#', name: '¿Cómo funciona?' },
        { id: 'link4', url: '#', name: 'Causa' },
        { id: 'link5', url: '#', name: 'Inicio Sesión' }
      ]
    }
  },
  methods: {
    screenSize: function () {
      if (this.mediaQuery.matches) {
        this.smallScreen = true
      } else {
        this.smallScreen = false
      }
    },
    toggleOffCanvas: function (ev) {
      this.activeCanvas = !this.activeCanvas

      this.activeCanvas ? this.$emit('activeCanvas') : this.$emit('inactiveCanvas')
    }
  },
  computed: {
    showNavigation: function () {
      return !this.smallScreen
    },
    showOffCanvas: function () {
      return this.smallScreen
    }
  },
  components: {
    Navigation,
    OffCanvas
  },
  created: function () {
    this.mediaQuery.addListener(this.screenSize)
    this.screenSize()
  },
  beforeDestroy: function () {
    this.mediaQuery.removeListener(this.screenSize)
  }
}
</script>

<style lang='scss' scoped>
@import '../Layout/Theme.scss';

/* Shared style between the register link and the banner */
.option {
  width: 100%;
  height: 67px;
  font-size: 22px;
  border-radius: $border;
}

header {

  position: fixed;
  width: 100%;
  background-color: white;
  height: 180px;
  box-shadow: 0 10px 15px 0 $gray-color;
  z-index: 2;

  span { color: white; }

  #offCanvasButton {

    width: 50px;
    height: 50px;
    background-color: white;
    border: 2px solid $dark-color;
    border-radius: $small-border;

    i {
      color: $dark-color;
    }
  }

  #raceLogo { max-width: 150px; }

  #headerLogo { max-width: 215px; }

  #registerContainer {
    width: 100%;
    height: 150px;
  }

  #registerLink {

    @extend .option;

    background-color: $main-bg-color;
    text-align: center;
    cursor: pointer;

    span { font-weight: bold; }
  }

  #collectedBanner {

    @extend .option;

    background-image: url('./assets/header-banner.png');

    span:last-child { font-weight: bold; }
  }
}

@include media-breakpoint-md {

  .option {
    font-size: 18px;
    padding: 0.02%;
  }
}

@include media-breakpoint-sm {

  .option { font-size: 15px; }

  header {

    height: 7.5em;

    #offCanvasButton {

      width: 3.3em;
      height: 3.3em;
      position: absolute;
      left: 1em;

      i {
        font-size: 35px;
      }
    }

    #raceLogo {
      width: 5em;
      margin: 0.3em;
    }

    #registerContainer {
      height: 3.5em;
    }

    #registerLink { width: 8.75em; }

    #collectedBanner { width: 9.75em; }
  }
}

@include media-breakpoint-xs {

  .option {
    font-size: 11px;
    border-radius: $small-border;
  }

  header {

    #raceLogo { width: 3em; }

    #registerLink { width: 8.5em; }

    #collectedBanner { width: 10em; }
  }
}
</style>
