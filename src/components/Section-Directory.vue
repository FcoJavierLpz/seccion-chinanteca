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
  </section>
</template>

<script>
import Business from './Business.vue';

export default {
  name: 'SectionDirectory',
  components: { Business },
};
</script>

<style lang="scss" scoped></style>
