<template>
<header class="bg-primary d-flex align-items-center p-3">
  <img src="../assets/img/logo.png" alt="">
  <label class="ms-auto" for="genre">
    Filtra per genere
    <select @change="$emit('change-genre', $event.target.value)"
      class="ms-auto"
      name="genre"
      id="genre"
    >
      <option value="">Tutti</option>
      <option
        v-for="option in genreOptions"
        :key="option"
        :value="option">{{ option }}</option>
    </select>
  </label>
  <label
    class="ms-auto" for="author"
    @input="$emit('search-author', $event.target.value.trim())">
    Cerca per autore
    <input type="text">
  </label>
</header>
</template>

<script>
export default {
  name: 'HeaderDisk',
  props: {
    genreOptions: Array,
  },
};
</script>

<style lang="scss" scoped>
header {
  img {
    width: 45px;
  }
}
</style>
