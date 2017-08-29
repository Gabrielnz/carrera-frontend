<template>
  <div class='row justify-content-center'>
    <div class='col-12 col-sm-10'>
      <div id='titleContainer' class='row justify-content-between no-gutters'>
        <div id='main' class='d-flex align-items-center justify-content-start'>
          <div id='titleBar'></div>
          <h3>TOP 10 DE CORREDORES</h3>
        </div>
        <div class='col-2 col-md-1 d-flex align-items-center justify-content-between'>
          <img src='./assets/title-icon.png'>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'title'
}
</script>

<style lang='scss' scoped>

@import '../Layout/Theme.scss';

#titleContainer {
  
  height: 70px;
  background-color: $white-color;
  margin: $vertical-space * 1.5 0;

  #main {

    h3 {
      margin-bottom: 0;
      font-weight: bold;
      font-size: 35px;
    }

    #titleBar {

      width: 30px;
      height: 100%;
      background-color: $main-bg-color;
    }

  }

  img {
    width: 50px;
    object-fit: contain;
  }
}

</style>
