<template>

<nav>
  <div class='container-fluid'>
    <div class='row justify-content-center'>
      <div class='col-12 col-md-10'>
        <ul id='navigationList' class='d-flex justify-content-between'>
          <li v-for='(link, index) in links'>
            <a :href='link.url' class='d-flex align-items-center justify-content-center'>{{ link.name }}</a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</nav>

</template>

<script>

export default {
  name: 'race-navigation',
  data () {
    return {
      links:
      [
        { id: 'link1', url: '/', name: 'Home' },
        { id: 'link2', url: '#', name: 'Corredores' },
        { id: 'link3', url: '#', name: '¿Cómo funciona?' },
        { id: 'link4', url: '#', name: 'Causa' },
        { id: 'link5', url: '#', name: 'Inicio Sesión' }
      ]
    }
  }
}

</script>

<style lang='scss' scoped>

@import '../../App.scss';

nav {
  margin: 20px 0;

  #navigationList {
    list-style: none;
    padding-left: 0;
    margin-bottom: 0;

    a {
      background-color: $main-bg-color;
      min-width: 150px;
      height: 50px;
      border-radius: $border;
      padding: 0 15px;
      color: white;
      font-size: 23px;
    }
  }
}

/* Large devices */
@media (max-width: 1199px) {

  nav {

    #navigationList {

      a {
        font-size: 20px;
        min-width: 7em;
      }
    }
  }
}

/* Medium devices */
@media (max-width: 991px) {

  nav {

    #navigationList {

      a {
        font-size: 15px;
      }
    }
  }
}

</style>