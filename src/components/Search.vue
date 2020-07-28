<template>
  <form action="#" class="search">
    <input
      type="text"
      @input="filter"
      v-model="search"
      class="search__input"
      placeholder="Buscar Negocio"
    />
    <button class="search__button" @click="filter">
      <svg class="search__icon">
        <use xlink:href="@/assets/img/sprite.svg#icon-magnifying-glass"></use>
      </svg>
    </button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      search: '',
    };
  },
  methods: {
    filter(e) {
      e.preventDefault();
      this.$emit('search-business', this.search);
    },
  },
};
</script>

<style lang="scss" scoped>
.search {
  flex: 0 0 40%;

  display: flex;
  align-items: center;
  justify-content: center;

  @include respond(phone) {
    order: 1;
    flex: 0 0 100%;
  }

  &__input {
    font-family: inherit;
    font-size: 1.8rem;
    color: inherit;
    background-color: $color-white;
    border: none;
    padding: 2rem 2rem;
    border-radius: 100px;
    width: 75%;
    transition: all 0.2s;
    margin-right: -3.25rem;

    &:focus {
      outline: none;
      width: 100%;
      background-color: $color-white;
    }

    &::-webkit-input-placeholder {
      font-weight: 100;
      color: var($color-grey-light-5);
    }
  }

  &__input:focus + &__button {
    background-color: v$color-grey-light-4;
  }

  &__button {
    border: none;
    background-color: $color-white;

    &:focus {
      outline: none;
    }

    &:active {
      transform: translateY(2px);
    }
  }

  &__icon {
    height: 2.5rem;
    width: 2.5rem;
    fill: $color-grey-dark-3;
  }
}
</style>
