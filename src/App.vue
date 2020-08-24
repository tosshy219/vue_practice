<template>
  <div id="app">
    <Picture></Picture>
    <br>
    <hr>
    <Gauge></Gauge>
    <hr>
  </div>
</template>

<script>
import Picture from './components/Picture.vue'
import Gauge from './components/Gauge.vue'

export default {
  components:{
    Picture,
    Gauge
  }
}
</script>

<style scoped>
#app{
  padding-top: 6rem;
  text-align: center;
}
</style>
