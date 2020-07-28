<template>
  <section class="section-directory" id="directory">
    <div class="u-center-text u-margin-bottom-big">
      <h2 class="heading-secondary">
        Directorio
      </h2>
    </div>
    <div class="row">
      <search></search>
    </div>
    <div class="row" v-for="commerce in business" :key="commerce.id">
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
    };
  },
};
</script>

<style lang="scss" scoped></style>
