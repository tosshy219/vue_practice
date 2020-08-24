<template>
  <div>
    <button @click="isActive = !isActive">切り替え</button>
    <br><br>
    <div class="pic" :class="{spin:isActive}"></div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      isActive:false
    }
  }
}
</script>

<style scoped>
.pic{
  width: 200px;
  height: 200px;
  background-color: tomato;
  transition: 1s;
  margin: 0 auto;
  margin-top: 2rem;
}
.spin{
  transform: rotate(360deg);
  border-radius: 50%;
  background-color: skyblue;
}


</style>