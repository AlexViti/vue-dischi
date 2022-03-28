<template>
  <div class="card-disk p-4 h-100 text-center bg-primary d-flex flex-column">
    <img class="img-fluid"
      :src="disk.poster"
      :alt="disk.title"
    />
    <h2 class="text-uppercase">{{ disk.title }}</h2>
    <div class="text-secondary fs-3 mt-auto">{{ disk.author }}</div>
    <div class="text-secondary fs-3">{{ disk.year }}</div>
  </div>
</template>

<script>
export default {
  name: 'CardDisk',
  props: {
    disk: Object,
  },
};
</script>

<style lang="scss" scoped>

</style>
