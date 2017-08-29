<template>
  <Layout>
    <Carousel :slides='slides' />
    <TitleSection />
  </Layout>
</template>

<script>

import Layout from '../Shared/Layout/Main.vue'
import TitleSection from '../Shared/Title/Main.vue'
import Carousel from './Carousel.vue'

export default {
  name: 'home',
  data: function () {
    return {
      slides:
      [
        {
          url: require('./assets/carousel.jpg'),
          alt: 'Primer slide'
        },
        {
          url: require('./assets/carousel.jpg'),
          alt: 'Segundo slide'
        },
        {
          url: require('./assets/carousel.jpg'),
          alt: 'Tercer slide'
        }
      ]
    }
  },
  components: {
    Layout,
    Carousel,
    TitleSection
  }
}

</script>

<style lang='scss' scoped>

@import '../Shared/Layout/Theme.scss';

</style>
