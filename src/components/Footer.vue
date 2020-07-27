<template>
  <footer class="footer">
    <div class="footer__logo-box">
      <picture class="footer__logo">
        <!-- <source
          srcset="img/logo-green-small-1x.png 1x, img/logo-green-small-2x.png 2x"
          media="(max-width: 37.5em)"
        /> -->
        <img

          alt="Full logo"
          src="@/assets/img/icon-logo.png"
        />
      </picture>
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
}
</style>
