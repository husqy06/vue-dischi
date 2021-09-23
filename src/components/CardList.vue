<template>
  <section>
    <div v-if="!loading" class="container">
      <Card :info='card' v-for="(card,index) in getFilterCards()" :key="index"/>
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
  props: ["filter"],
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
            console.log(res.data.response)
          })
          .catch(err => {
            console.log("Error ",err);
          })    
    },
    getFilterCards() {
      if(this.filter === ""){
        return this.cardlist
      }

      const filterCards = [];
      for(let i in this.cardlist) {
        if(this.cardlist[i].genre === this.filter)
        filterCards.push(this.cardlist[i])
      }
      return filterCards;
    } 
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../style/general.scss';
</style>
