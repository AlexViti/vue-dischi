<template>
  <div id="app" class="text-white">
    <header-disk />
    <main-disk />
  </div>
</template>

<script>
import HeaderDisk from './components/HeaderDisk.vue';
import MainDisk from './components/MainDisk.vue';

export default {
  name: 'App',
  components: {
    HeaderDisk,
    MainDisk,
  },
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap');
@import './assets/styles/_variables.scss';
@import '~bootstrap/scss/bootstrap.scss';
</style>
