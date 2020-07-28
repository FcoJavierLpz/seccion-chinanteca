<template>
  <section class="section-contact">
    <div class="row">
      <div class="contact">
        <div class="contact__form">
          <v-form></v-form>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import VForm from '@/components/VForm.vue';

export default {
  name: 'SectionContact',
  components: { VForm },
};
</script>

<style lang="scss" scoped></style>
