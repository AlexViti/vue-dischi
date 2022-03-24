<template>
  <div class="card-disk w-100">
    <img class="img-fluid"
      :src="diskData.poster"
      :alt="diskData.title"
    />
  </div>
</template>

<script>
export default {
  name: 'CardDisk',
  props: {
    diskData: Object,
  },
};
</script>

<style lang="scss" scoped>

</style>
