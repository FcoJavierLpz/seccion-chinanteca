<template>
  <header class="header">
    <div class="header__logo-box">
      <img src="@/assets/img/logo-white.svg" alt="Logo" class="header__logo" />
    </div>
    <div class="header__text-box">
      <h1 class="heading-primary">
        <span class="heading-primary--main">Sección Chinanteca</span>
        <q class="heading-primary--sub">La solidaridad como acto revolucionario</q>
      </h1>
      <a href="#directory" class="btn btn--white btn--animated">Comenzar a buscar</a>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.header {
  height: 85vh;
  background-image: linear-gradient(
      to right bottom,
      rgba($color-primary-light, 0.8),
      rgba($color-primary-dark, 0.8)
    ),
    url(~@/assets/img/bg-valle-nal.jpg);
  background-size: cover;
  background-position: center;
  position: relative;
  background-blend-mode: darken;

  @supports (clip-path: polygon(0 0)) or (-webkit-clip-path: polygon(0 0)) {
    -webkit-clip-path: polygon(0 0, 100% 0, 100% 75vh, 0 100%);
    clip-path: polygon(0 0, 100% 0, 100% 75vh, 0 100%);
    height: 95vh;
  }

  @media only screen and (min-resolution: 192dpi) and (min-width: 37.5em),
    only screen and (-webkit-min-device-pixel-ratio: 2) and (min-width: 37.5em),
    only screen and (min-width: 125em) {
    background-image: linear-gradient(
        to right bottom,
        rgba($color-primary-light, 0.8),
        rgba($color-primary-dark, 0.8)
      ),
      url(~@/assets/img/bg-valle-nal.jpg);
  }

  @include respond(phone) {
    -webkit-clip-path: polygon(0 0, 100% 0, 100% 85vh, 0 100%);
    clip-path: polygon(0 0, 100% 0, 100% 85vh, 0 100%);
  }

  &__logo-box {
    position: absolute;
    top: 4rem;
    left: 4rem;
  }

  &__logo {
    font-size: 2rem;
    color: $color-white;
  }

  &__text-box {
    position: absolute;
    top: 40%;
    left: 50%;
    transform: translate(-50%, -50%);
    text-align: center;
  }
}
</style>
