<template>
  <div class="wrapper">
    <Header />
    <Gallery />
  </div>
</template>

<script>
  import Header from './components/Header.vue';
  import Gallery from './components/Gallery.vue';
  export default {
    name: 'App',
    components: {
      Header,
      Gallery,
    },
  };
</script>

<style></style>
