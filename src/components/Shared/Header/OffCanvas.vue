<template>
<nav :class='{active}'>
  <ul id='offCanvasList'>
    <li v-for='(link, index) in links'>
      <a :href='link.url'><b>{{ link.name }}</b></a>
    </li>
  </ul>
</nav>
</template>

<script>
export default {
  name: 'offcanvas',
  props: ['active', 'links']
}
</script>

<style lang='scss' scoped>
@import '../Layout/Theme.scss';

.active {
  left: 0;
}

nav {
  
  position: fixed;
  top: 7.5em;
  left: -100%;
  width: 60vw;
  height: calc(100vh - 7.5em);
  background-color: white;
  padding-top: 15px;
  z-index: 1;
  transition: 0.3s;

  #offCanvasList {

    list-style: none;
    padding: 0 1.5em;
    margin: 0;

    li {

      display: flex;
      justify-content: center;
      padding: 15px 0;
      border-bottom: 1px solid $dark-color;

      a {
        color: $dark-color;
      }
    }
  }
}

@include media-breakpoint-xs {

}
</style>