<template>
  <header class="d-flex align-items-center">
    <div class="container-fluid">
      <div class="row">
        <div class="col-2 d-md-none">BurguerMenu</div>
        <div class="col-2 col-md-4 d-flex align-items-center justify-content-center">
          <a href="#">
            <img class="raceLogo" src="../assets/logo.png">
          </a>
        </div>
        <div class="col-md-4 d-none d-md-flex align-items-center justify-content-center">
          <img class="headerLogo" src="../assets/header-logo.png">
        </div>
        <div class="col-8 col-md-4 d-flex align-items-center justify-content-center">
          <div class="registerContainer d-flex flex-column align-items-center justify-content-center">
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

<style scoped>

header {
  background-color: white;
  height: 180px;
  box-shadow: 0 10px 15px 0 #CACACA;
}

span {
  color: white;
}

.container-fluid {
  max-width: 1305px;
}

.raceLogo {
  max-width: 150px;
}

.headerLogo {
  max-width: 215px;
}

.registerContainer {
  width: 100%;
}

#registerLink, #collectedBanner {
  width: 100%;
  height: 70px;
  font-size: 23px;
}

#registerLink span, #collectedBanner span:last-child {
  font-weight: bold;
}

#registerLink {
  background-color: #44A041;
  border-radius: 15px;
  text-align: center;
}

#collectedBanner {
  background-image: url("../assets/header-banner.png");
  margin-top: 10px;
  border-radius: 7px;
}

@media (max-width: 991px) {

  #registerLink, #collectedBanner {
    font-size: 1.5em;
    padding: 0.02%;
    font-size: 1em;
  }

}

@media (max-width: 767px) {}

@media (max-width: 575px) {}

</style>
