<template>
  <div>
    <Header></Header>
    <main>
      <section-about></section-about>
      <section-directory></section-directory>
      <section-contact></section-contact>
    </main>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import SectionDirectory from '@/components/Section-Directory.vue';
import SectionAbout from '@/components/Section-About.vue';
import SectionContact from '@/components/Section-Contact.vue';
import Footer from '@/components/Footer.vue';

export default {
  name: 'Home',
  components: {
    Header,
    SectionDirectory,
    SectionAbout,
    SectionContact,
    Footer,
  },
};

</script>

<style lang="scss" scoped>

</style>
