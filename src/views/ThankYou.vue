<template>
  <div>
    <div class="thank-you">
      <img
        class="thank-you__img"
        src="@/assets/img/illustrations/success.svg"
        alt="Registro con exito"
      />
      <h3 class="heading-success u-margin-bottom-small">
        ¡Gracias por registrarte!
      </h3>
      <p class="paragraph u-margin-bottom-medium">
        Tú información será evaluada, en caso de cumplir los requisitos, te notifcaremos a los
        números proporcionados.
      </p>
      <router-link to="/" class="btn btn--green">Finalizar</router-link>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.thank-you {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  height: 100vh;

  &__img {
    width: 35%;
  }
}

.heading-success {
  font-size: 3rem;
  text-transform: uppercase;
  font-weight: 700;
  display: inline-block;
  background-image: linear-gradient(to right, $color-primary-light, $color-primary-dark);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  letter-spacing: .2rem;
  margin-top: 2rem;

  @include respond(tab-port) {
      font-size: 2.5rem;
  }

  @include respond(phone) {
      font-size: 2rem;
  }
}

</style>
