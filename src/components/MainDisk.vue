<template>
  <main class="container py-5">
    <div class="row row-cols-2 row-cols-md-3 row-cols-lg-4 row-cols-xl-5 g-5">
      <div class="col" v-for="(disk, index) in filteredDisks" :key='index'>
        <card-disk :disk="disk" />
      </div>
    </div>
  </main>
</template>

<script>
import CardDisk from './CardDisk.vue';

export default {
  name: 'MainDisk',
  components: {
    CardDisk,
  },
  computed: {
    filteredDisks() {
      // eslint-disable-next-line max-len
      return this.disks.filter((disk) => (this.selectedGenre === '' ? disk : disk.genre === this.selectedGenre) && disk.author.toLowerCase().includes(this.authorSearch));
    },
  },
  props: {
    disks: Array,
    selectedGenre: String,
    authorSearch: String,
  },
};
</script>

<style lang="scss" scoped>

</style>
