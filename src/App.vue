<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style lang='scss'>

@import './components/Shared/Layout/Theme.scss';

a:hover { text-decoration: none !important; }

#app { font-family: 'Roboto', sans-serif; }

/* Default responsive typography */

html { font-size: 32px; }

@include media-breakpoint-lg {
  html { font-size: 28px; }
}

@include media-breakpoint-md {
  html { font-size: 20px; }
}

@include media-breakpoint-sm {
  html { font-size: 16px; }
}

@include media-breakpoint-xs {
  html { font-size: 14px; }
}

</style>
