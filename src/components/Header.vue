<template>
  <header>
    <img src="../assets/img/logo.png" alt="" srcset="">

    <select v-model="selected" @change="$emit('filterSelected', selected)" class="select">
      <option value="">Seleziona il genere</option>
      <option value="Rock">Rock</option>
      <option value="Pop">Pop</option>
      <option value="Jazz">Jazz</option>
      <option value="Metal">Metal</option>
    </select>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      selected: "",
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../style/general.scss';
</style>
