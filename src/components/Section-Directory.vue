<template>
  <section class="section-directory" id="directory">
    <div class="u-center-text u-margin-bottom-big">
      <h2 class="heading-secondary">
        Directorio
      </h2>
    </div>
    <div class="row">
      <business></business>
    </div>
    <div class="row">
      <div class="col-1-of-3">
        <card></card>
      </div>
    </div>
  </section>
</template>

<script>
import Business from './Business.vue';
import Card from './Card.vue';

export default {
  name: 'SectionDirectory',
  components: { Business, Card },
};
</script>

<style lang="scss" scoped></style>
