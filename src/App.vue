<template>
  <div id="app" class="text-white">
    <header-disk
      @change-genre="setGenreSelected"
      @search-author="setAuthor"
      :genre-options="genreOptions"
    />
    <main-disk :disks="disks" :selected-genre="selectedGenre" :author-search="authorSearch" />
  </div>
</template>

<script>
import axios from 'axios';
import HeaderDisk from './components/HeaderDisk.vue';
import MainDisk from './components/MainDisk.vue';

export default {
  name: 'App',
  components: {
    HeaderDisk,
    MainDisk,
  },
  computed: {
    genreOptions() {
      return [...new Set(this.disks.map((el) => el.genre))];
    },
  },
  created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((res) => { this.disks = res.data.response; })
      .catch(() => { console.log('error'); });
  },
  data() {
    return {
      disks: [],
      selectedGenre: '',
      authorSearch: '',
    };
  },
  methods: {
    setGenreSelected(value) {
      this.selectedGenre = value;
    },
    setAuthor(value) {
      this.authorSearch = value;
    },
  },
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap');
@import './assets/styles/_variables.scss';
@import '~bootstrap/scss/bootstrap.scss';
</style>
