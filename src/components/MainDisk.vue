<template>
  <main class="container">
    <div class="row row-cols-5">
      <div class="col" v-for="(disk, index) in disks" :key='index'>
        <card-disk :disk-data="disk" />
      </div>
    </div>
  </main>
</template>

<script>
import axios from 'axios';
import CardDisk from './CardDisk.vue';

export default {
  name: 'MainDisk',
  components: {
    CardDisk,
  },
  data() {
    return {
      disks: null,
    };
  },
  created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((res) => { this.disks = res.data.response; })
      .catch(() => { console.log('error'); });
  },
};
</script>

<style lang="scss" scoped>

</style>
