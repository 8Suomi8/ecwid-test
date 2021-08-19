<template>
  <div class="wrapper">
    <Header />
    <Gallery />
    <Features />
    <Intro />
  </div>
</template>

<script>
  import Header from './components/Header.vue';
  import Gallery from './components/Gallery.vue';
  import Features from './components/Features.vue';
  import Intro from './components/Intro.vue';

  export default {
    name: 'App',
    components: {
      Header,
      Gallery,
      Features,
      Intro,
    },
  };
</script>

<style scope lang="scss">
  @import './assets/styles/fonts.css';
  @import './assets/styles/main.scss';

  .wrapper {
    padding-bottom: 80px;
  }
</style>
