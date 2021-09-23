<template>
  <main>
    <CardList :filter="filter"/>
  </main>
</template>

<script>

import CardList from './CardList.vue'

export default {
  name: 'Main',
  components: {
    CardList
  },
  props: ['filter'],
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../style/general.scss';
</style>
