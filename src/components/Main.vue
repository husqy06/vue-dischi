<template>
  <main>
    <CardList/>
  </main>
</template>

<script>

import CardList from './components/CardList.vue'

export default {
  name: 'Main',
  components: {
    CardList
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../style/general.scss';
</style>
