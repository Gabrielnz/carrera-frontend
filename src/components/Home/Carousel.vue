<template>
  <div class='row'>
    <div class='col-12'>
      <div id='carousel' class='carousel slide' data-ride='carousel'>
        <div class='carousel-inner'>
          <template v-for='(slide, index) in slides'>
            <div :id="'slide' + index" class='carousel-item' :class='{ active: index == 0 }'>
              <img class='d-block w-100' :src='slide.url' :alt='slide.alt'>
            </div>
          </template>
        </div>
        </div>
        <a class='carousel-control-prev' href='#carousel' role='button' data-slide='prev'>
          <span class='carousel-control-prev-icon' aria-hidden='true'></span>
          <span class='sr-only'>Previous</span>
        </a>
        <a class='carousel-control-next' href='#carousel' role='button' data-slide='next'>
          <span class='carousel-control-next-icon' aria-hidden='true'></span>
          <span class='sr-only'>Next</span>
        </a>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'carousel',
  props: ['slides']
}

</script>

<style lang='scss' scoped>

@import '../Shared/Layout/Theme.scss';

#carousel {

  img {
    height: 600px;
    object-fit: cover;

  }
}

@include media-breakpoint-lg {

  #carousel {
    img { height: 500px; }
  }
}

@include media-breakpoint-md {

  #carousel {
    img { height: 400px; }
  }
}

@include media-breakpoint-sm {

  #carousel {
    img { height: 350px; }
  }
}

@include media-breakpoint-xs {

  #carousel {
    img { height: 250px; }
  }
}

</style>
