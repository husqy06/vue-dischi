<template>
  <section class="container">
    <div v-if="!loading">
      <Card :info='card' v-for="(card,index) in cardlist" :key="index"/>
    </div>
    <Loader v-else />
  </section>
</template>

<script>
import axios from 'axios';
import Card from './Card.vue';
import Loader from './Loader.vue';

export default {
  name: 'Cardlist',
  components: {
    Card,
    Loader
  },
  data() {
    return {
      APIUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
      cardlist: [],
      loading: true
    }
  },
  created() {
    this.getCard();
  },
  methods: {
    getCard() {
      axios
          .get(this.APIUrl)
          .then( res => {
            this.cardlist = res.data.response;
            setTimeout( () => {this.loading = false;},2000)
          })
          .catch(err => {
            console.log("Error ",err);
          })
    }
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../style/general.scss';
</style>
