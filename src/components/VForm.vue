<template>
  <form
    action="https://send.pageclip.co/U3QSPafLGcDmXA6nw9y9mew0UmBI4S71"
    class="pageclip-form form"
    method="post"
    @submit.prevent="onSubmit"
  >
    <div class="u-margin-bottom-medium">
      <h2 class="heading-secondary">
        Registra tu negocio
      </h2>
    </div>

    <div class="form__group">
      <input
        type="text"
        class="form__input"
        placeholder="Nombre del negocio"
        name="name"
        v-model="name"
        id="name"
        required
      />
      <label for="name" class="form__label">Nombre del negocio</label>
    </div>

    <div class="form__group">
      <input
        type="text"
        class="form__input"
        placeholder="Dirección"
        name="address"
        v-model="address"
        id="address"
        required
      />
      <label for="address" class="form__label">Dirección</label>
    </div>

    <div class="form__group">
      <input
        type="text"
        class="form__input"
        placeholder="Teléfono"
        name="phone"
        v-model="phone"
        id="phone"
        required
      />
      <label for="phone" class="form__label">Teléfono</label>
    </div>

    <div class="form__group">
      <input
        type="text"
        class="form__input"
        placeholder="Whatsapp"
        name="whatsapp"
        v-model="whatsapp"
        id="whatsapp"
        required
      />
      <label for="whatsapp" class="form__label">Whatsapp</label>
    </div>

    <div class="form__group">
      <textarea
        class="form__input"
        cols="20"
        rows="3"
        placeholder="¿Qué vendes?"
        name="description"
        v-model="description"
        id="description"
        required
      ></textarea>
      <label for="description" class="form__label">¿Qué vendes?</label>
    </div>

    <div class="form__group">
      <input
        type="file"
        class="form__input"
        placeholder="Sube tu logo"
        name="logo"
        id="logo"
        required
      />
      <label for="logo" class="form__label">Sube tu logo</label>
    </div>

    <div class="form__group">
      <button type="submit" class="pageclip-form__submit btn btn--green">
        <span>Registrar</span>
      </button>
    </div>
    <div class="animated fadeInDown alert alert--success" role="alert" v-show="isSending">
      <button
        type="button"
        class="close"
        data-dismiss="alert"
        aria-label="Close"
        @click="isSending = false"
      >
        <span aria-hidden="true">×</span>
      </button>
      <strong>¡Gracias por registrarte {{ name }}!,</strong>
      tu información será evaluada, en caso de cumplir los requisitos te
      notifcaremos a los números proporcionados
    </div>
  </form>
</template>

<script>
export default {
  name: 'VForm',
  data() {
    return {
      errors: [],
      name: null,
      address: null,
      phone: null,
      whatsapp: null,
      description: null,
      logo: null,
      isSending: false,
    };
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();
      this.isSending = true;
    },
  },
};
</script>

<style lang="scss" scoped>
.form {
  &__group:not(:last-child) {
    margin-bottom: .8rem;
  }

  &__input {
    font-size: 1.4rem;
    font-family: inherit;
    color: inherit;
    padding: 1.2rem 2rem;
    border-radius: 2px;
    background-color: rgba($color-white, 0.5);
    border: none;
    border-bottom: 3px solid transparent;
    width: 90%;
    display: block;
    transition: all 0.3s;

    @include respond(tab-port) {
      width: 100%;
    }

    &:focus {
      outline: none;
      box-shadow: 0 1rem 2rem rgba($color-black, 0.1);
      border-bottom: 3px solid $color-primary;
    }

    &:focus:invalid {
      border-bottom: 3px solid $color-secondary-dark;
    }

    &::-webkit-input-placeholder {
      color: $color-grey-dark-2;
    }
  }

  &__label {
    font-size: 1.2rem;
    font-weight: 700;
    margin-left: 2rem;
    margin-top: 0.7rem;
    display: block;
    transition: all 0.3s;
  }

  &__input:placeholder-shown + &__label {
    opacity: 0;
    visibility: hidden;
    transform: translateY(-4rem);
  }

  &__radio-group {
    width: 49%;
    display: inline-block;

    @include respond(tab-port) {
      width: 100%;
      margin-bottom: 2rem;
    }
  }

  &__radio-input {
    display: none;
  }

  &__radio-label {
    font-size: $default-font-size;
    cursor: pointer;
    position: relative;
    padding-left: 4.5rem;
  }

  &__radio-button {
    height: 3rem;
    width: 3rem;
    border: 5px solid $color-primary;
    border-radius: 50%;
    display: inline-block;
    position: absolute;
    left: 0;
    top: -0.4rem;

    &::after {
      content: "";
      display: block;
      height: 1.3rem;
      width: 1.3rem;
      border-radius: 50%;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background-color: $color-primary;
      opacity: 0;
      transition: opacity 0.2s;
    }
  }

  &__radio-input:checked ~ &__radio-label &__radio-button::after {
    opacity: 1;
  }

  .alert {
    font-size: $default-font-size;
    color: $color-primary;
    padding: 1.3rem;
    margin-bottom: 2rem;
    border: .1rem solid transparent;
    border-radius: .4rem;
    margin-right: 3rem;

    &--success {
      color: #3c763d;
      background-color: #dff0d8;
      border-color: #d6e9c6;
    }
  }

  button.close {
    -webkit-appearance: none;
    padding: 0;
    cursor: pointer;
    background: 0 0;
    border: 0;
  }

  .close {
    float: right;
    font-size: 2.1rem;
    font-weight: 700;
    line-height: 1;
    color: #000;
    text-shadow: 0 1px 0 $color-white;
    filter: alpha(opacity=20);
    opacity: 0.2;
  }
}
</style>
