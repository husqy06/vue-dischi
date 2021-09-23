<template>
  <div id="app">
    <Header @filterSelected="onfilterSelected"/>
    <Main :filter="filter"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data() {
    return {
      filter: ""
    }
  },
  methods: {
    onfilterSelected(value) {
      this.filter = value;
    }
  }
}
</script>

<style scoped lang='scss'>
@import './style/general.scss';
</style>


