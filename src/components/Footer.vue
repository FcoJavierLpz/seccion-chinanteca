<template>
  <footer class="footer">
    <div class="footer__logo-box">
      <picture class="footer__logo">
        <img
          alt="logo verde"
          src="@/assets/img/logo-green.svg"
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
