<template>
  <div class="business">
    <figure class="business__shape">
      <img
        :src="
          business.image
            ? require(`@/assets/${this.business.image}`)
            : require(`@/assets/${this.imageDefault}`)
        "
        :alt="business.name"
        class="business__img"
      />
      <figcaption class="business__caption">
        {{ business.name }}
      </figcaption>
    </figure>
    <div class="business__text">
      <h3 class="heading-tertiary u-margin-bottom-small">
        {{ business.name }}
      </h3>
      <h4>Datos de Contacto</h4>
      <div class="business__contact-details">
        <p>
          {{ business.address }}
        </p>
        <ul>
          <li>
            <a href="">
              <i class="icofont-phone"></i>
              <span> {{ business.phone }} </span>
            </a>
          </li>
          <li>
            <a href="">
              <i class="icofont-whatsapp"></i>
              <span> {{ business.whatsapp }} </span>
            </a>
          </li>
          <li>
            <a href="">
              <i class="icofont-facebook-messenger"></i>
              <span>Messenger</span>
            </a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    business: {
      type: Object,
      default: () => {},
    },
  },
  data() {
    return {
      imageDefault: 'img/illustrations/store.svg',
    };
  },
};
</script>

<style lang="scss" scoped>
.business {
  width: 75%;
  margin: 0 auto;
  box-shadow: 0 3rem 6rem rgba($color-black, 0.1);
  background-color: rgba($color-white, 0.6);
  border-radius: 3px;
  padding: 3rem;
  padding-left: 9rem;
  font-size: $default-font-size;
  transform: skewX(-12deg);

  @include respond(tab-port) {
    width: 100%;
    padding: 4rem;
    padding-left: 7rem;
  }

  @include respond(phone) {
    transform: skewX(0);
  }

  &__shape {
    width: 15rem;
    height: 15rem;
    float: left;
    transform: translateX(-3rem) skewX(12deg);
    position: relative;
    overflow: hidden;
    border-radius: 50%;

    @supports (clip-path: polygon(0 0)) or (-webkit-clip-path: polygon(0 0)) {
      -webkit-clip-path: circle(50% at 50% 50%);
      clip-path: circle(50% at 50% 50%);
      -webkit-shape-outside: circle(50% at 50% 50%);
      shape-outside: circle(50% at 50% 50%);
      border-radius: none;
    }

    @include respond(tab-port) {
      float: none;
      margin: 0 auto;
    }

    @include respond(phone) {
      transform: translateX(-3rem) skewX(0);
    }
  }

  &__img {
    height: 100%;
    transform: translateX(0) scale(1.2);
    backface-visibility: hidden;
    transition: all 0.5s;
  }

  &__text {
    transform: skewX(12deg);

    @include respond(phone) {
      transform: skewX(0);
    }
  }

  &__caption {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, 20%);
    color: $color-white;
    text-transform: uppercase;
    font-size: 1.7rem;
    text-align: center;
    opacity: 0;
    transition: all 0.5s;
    backface-visibility: hidden;
  }

  &:hover &__caption {
    opacity: 1;
    transform: translate(-50%, -50%);
  }

  &:hover &__img {
    transform: translateX(0) scale(1);
    filter: blur(3px) brightness(80%);
  }

  &__contact-details {
    padding: 1rem;

    @include respond(tab-port) {
      padding: 0;
    }

    ul {
      list-style: none;

      li {
        text-align: center;
        font-size: 1.5rem;
        padding: 1rem;
        display: inline-block;

        @include respond(tab-port) {
          display: block;
          text-align: justify;
          padding: 1rem 0;

          &:not(:last-child) {
            border-right: 0;
            border-bottom: 1px solid $color-grey-light-2;
          }
        }

        &:not(:last-child) {
          border-right: 1px solid $color-grey-light-2;
        }

        &:first-child {
          padding-left: 0;
        }

        a {
          text-decoration: none;
        }
      }

      [class^="icofont-"] {
        font-size: 2.5rem;

        &:not(:last-child) {
          margin-right: 0.4rem;
        }
      }
    }

    .icofont-phone {
      color: $color-grey-dark;
    }

    .icofont-whatsapp {
      background-image: linear-gradient(to right, $color-primary-light, $color-primary-dark);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .icofont-facebook-messenger {
      background-image: linear-gradient(#00c6ff, #0078ff);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }
  }
}
</style>
