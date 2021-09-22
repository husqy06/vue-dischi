<template>
  <section class="container">
    <Card :info='card'/>

  </section>
</template>

<script>
import axios from 'axios';
import Card from './card.vue';

export default {
  name: 'Cardlist',
  components: {
    Card
  },
  data() {
    return {
      APIUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
      cardlist: []
    }
  },
  created() {
    this.getCards();
  },
  methods: {
    getCards() {
      axios
          .get(this.APIUrl)
          .then( res => {
            this.cardlist = res.data;
          })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../style/general.scss';
</style>
