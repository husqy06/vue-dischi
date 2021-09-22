<template>
  <section class="container">
    <Card :info='card' v-for="(card,index) in cardlist" :key="index"/>
  </section>
</template>

<script>
import axios from 'axios';
import Card from './Card.vue';

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
  mounted() {
    axios
          .get(this.APIUrl)
          .then( res => {
            this.cardlist = res.data.response;
          })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../style/general.scss';
</style>
