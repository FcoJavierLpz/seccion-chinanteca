<template>
  <section class="section-directory" id="directory">
    <div class="u-center-text u-margin-bottom-big">
      <h2 class="heading-secondary">
        Directorio
      </h2>
    </div>
    <div class="row">
      <search @search-business="emitSearch"></search>
    </div>
    <div class="row">
      <h3 class="heading-tertiary u-center-text" v-show="!filteredBusiness.length">
        Ups! Lo sentimos, No existen registros de este negocio
      </h3>
    </div>
    <div class="row" v-for="commerce in filteredBusiness" :key="commerce.id">
      <business :business="commerce"></business>
    </div>
  </section>
</template>

<script>
import Business from './Business.vue';
import Search from './Search.vue';
import api from './api/business.json';

export default {
  name: 'SectionDirectory',
  components: { Business, Search },
  data() {
    return {
      business: api,
      filter: '',
    };
  },
  methods: {
    emitSearch(search) {
      this.filter = search;
    },
  },
  computed: {
    filteredBusiness() {
      return this.business
        .filter((commerce) => commerce.name.toLowerCase().includes(this.filter.toLowerCase()));
    },
  },
};
</script>

<style lang="scss" scoped></style>
