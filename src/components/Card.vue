<template>
  <div>
    <img :src="info.image" alt="">
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: ['info']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../style/general.scss';
</style>
