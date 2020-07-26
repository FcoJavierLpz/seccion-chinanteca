<template>
  <div id="app">
    <Header></Header>
    <main>
      <section-directory></section-directory>
    </main>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import SectionDirectory from '@/components/Section-Directory.vue';
import Footer from '@/components/Footer.vue';

export default {
  name: 'App',
  components: {
    Header,
    SectionDirectory,
    Footer,
  },
};
</script>
