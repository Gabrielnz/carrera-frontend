<template>
  <header class="d-flex align-items-center">
    <div class="container-fluid">
      <div class="row">
        <div class="col-2 d-md-none">Menu</div>
        <div class="col-2 col-md-4 d-flex align-items-center justify-content-center">
          <a href="#">
            <img id="raceLogo" src="../assets/logo.png">
          </a>
        </div>
        <div class="col-md-4 d-none d-md-flex align-items-center justify-content-center">
          <img id="headerLogo" src="../assets/header-logo.png">
        </div>
        <div class="col-8 col-md-4 d-flex align-items-center justify-content-center">
          <div id="registerContainer" class="d-flex flex-row-reverse justify-content-around flex-md-column align-items-center justify-md-content-center">
            <a id="registerLink" class="d-flex align-items-center justify-content-center" href="#"><span>Regístrate <br> como Corredor</span></a>
            <div id="collectedBanner" class="d-flex flex-column align-items-center justify-content-center">
              <span>Monto Recaudado</span>
              <span>$1,907,632 MXN</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'race-header'
}
</script>

<style lang="scss" scoped>

/* Shared style between the register link and the banner */
.option {
  width: 100%;
  height: 67px;
  font-size: 22px;
  border-radius: 10px;
}

header {

  @import "../App.scss";

  background-color: white;
  height: 180px;
  box-shadow: 0 10px 15px 0 $gray-color;

  span { color: white; }

  .container-fluid { max-width: 1305px; }

  #raceLogo { max-width: 150px; }

  #headerLogo { max-width: 215px; }

  #registerContainer {
    width: 100%;
    height: 100%;
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

    background-image: url("../assets/header-banner.png");

    span:last-child { font-weight: bold; }
  }
}

/* Medium devices */
@media (max-width: 991px) {

  .option {
    font-size: 1.25em;
    padding: 0.02%;
  }
}

/* Small devices */
@media (max-width: 767px) {

  .option { font-size: 1em; }

  header {

    height: 7.5em;

    #raceLogo {
      width: 5em;
      margin: 0.3em;
    }

    #registerContainer {
      margin: 0 0.5em;
      height: 3.5em;
    }

    #registerLink { width: 8.75em; }

    #collectedBanner { width: 9.75em; }
  }
}

/* Extra small devices */
@media (max-width: 575px) {

  .option {
    font-size: 0.75em;
    border-radius: 0.65em;
  }

  header {

    #raceLogo { width: 4.5em; }

    #registerLink { width: 8.5em; }

    #collectedBanner { width: 10em; }
  }
}

</style>
