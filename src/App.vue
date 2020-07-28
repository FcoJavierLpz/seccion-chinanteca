<template>
  <div id="app">
    <Header></Header>
    <main>
      <section-about></section-about>
      <section-directory></section-directory>
    </main>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import SectionDirectory from '@/components/Section-Directory.vue';
import SectionAbout from '@/components/Section-About.vue';
import Footer from '@/components/Footer.vue';

export default {
  name: 'App',
  components: {
    Header,
    SectionDirectory,
    SectionAbout,
    Footer,
  },
};
</script>
