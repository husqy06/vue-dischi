<template>
  <div class="card">
    <img :src="info.poster" alt="">
    <span class="title">{{ info.title }}</span>
    <span class="subtitle">{{ info.author }}</span>
    <span class="subtitle">{{ info.year }}</span>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: ['info'],
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../style/general.scss';
</style>
