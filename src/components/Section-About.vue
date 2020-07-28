<template>
  <section class="section-about">
    <div class="u-center-text u-margin-bottom-big">
      <h2 class="heading-secondary">
        Nosotros
      </h2>
    </div>

    <div class="row">
      <div class="col-1-of-2">
        <h3 class="heading-tertiary u-margin-bottom-small">
          Seccion Chinanteca
        </h3>
        <p class="paragraph">
          Esta página fue creada en apoyo al comercio local de nuestra comunidad con el unico
          objetivo de reactivar nuestra economia.
        </p>
      </div>
      <div class="col-1-of-2">
        <div class="composition">
          <img
            srcset="
              @/assets/img/illustrations/about-5.svg  300w,
              @/assets/img/illustrations/about-5.svg 1000w
            "
            sizes="(max-width: 56.25em) 20vw, (max-width: 37.5em) 30vw, 300px"
            alt="Photo 1"
            class="composition__photo"
            src="@/assets/img/illustrations/about-5.svg"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.composition {
  text-align: center;
  &__photo {
    width: 80%;
  }
}
</style>
