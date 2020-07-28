<template>
  <footer class="footer">
    <div class="footer__logo-box">
      <picture class="footer__logo">
        <img alt="logo verde" src="@/assets/img/logo-green.svg" />
      </picture>
      <p class="footer__copyright">
        © Copyright 2020
      </p>
      <p class="footer__author">
        Design by
        <a href="https://fcojavierlpz.netlify.app/" target="__blank" class="footer__link">
          Francisco J. López
        </a>
      </p>
    </div>
  </footer>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.footer {
  background-color: $color-grey-dark-3;
  padding: 10rem 0;
  font-size: 1.4rem;
  color: $color-grey-light-1;

  @include respond(tab-port) {
    padding: 8rem 0;
  }

  &__logo-box {
    text-align: center;
    margin-bottom: 8rem;

    @include respond(tab-port) {
      margin-bottom: 6rem;
    }
  }

  &__logo {
    width: 15rem;
    height: auto;
  }

  &__copyright {
    font-size: 1.5rem;
  }

  &__author {
    font-size: 1.6rem;
    margin: 2rem;
  }

  &__link {
    &:link,
    &:visited {
      color: $color-grey-light-1;
      background-color: $color-grey-dark-3;
      text-decoration: none;
      display: inline-block;
      transition: all 0.2s;
    }

    &:hover,
    &:active {
      color: $color-primary;
      box-shadow: 0 1rem 2rem rgba($color-black, 0.4);
      transform: scale(1.3);
    }
  }
}
</style>
