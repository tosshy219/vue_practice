<template>
  <div>
    <br>
    <br>
    <h1>攻撃するたびに弱っていくスライム</h1>
    <div class="monster" :style="{opacity:vanish }">
      <div class="eye left" :style="{transform:'rotate('+leftEye+ 'deg)'}"></div>
      <div class="eye right" :style="{transform:'rotate('+rightEye+ 'deg)'}"></div>
    </div>
    <br>
    <h2>スライムのHP</h2>
    <div id="health">
      <div :style="{width:health + '%'}"></div>
    </div>

    <button @click="attack" v-show="!ended" class="button">Attack</button>
    <button @click="heal" class="button">Heal</button>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
  </div>
</template>

<script>
export default {
  data(){
    return{
      health:100,
      ended:false,
      vanish:1,
      leftEye:30,
      rightEye:-30
    }
  },
  methods:{
    attack(){
      this.health -=10;
      this.vanish -=0.1;
      this.leftEye -=9;
      this.rightEye +=9;
      if(this.health <= 0){
        this.ended=true
      }
    },
    heal(){
      this.health =100;
      this.ended=false;
      this.vanish=1;
      this.leftEye=30;
      this.rightEye=-30;
    }
  }
}
</script>

<style scoped>
*{
  user-select: none;
}
#health{
  width: 200px;
  border: 2px solid;
  margin: 0 auto;
  margin-bottom: 2rem;
}
#health div{
  background-color:lightpink ;
  height: 20px;
}
.button{
  margin-right: 1rem;
}
.monster{
  width: 200px;
  border-radius: 100px 100px 40px 40px ;
  background-color: lightgreen;
  height: 100px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: space-around;
}
.monster .eye{
  background-color: lemonchiffon;
  width: 30px;
  height: 10px;
}
.monster .left{
  transform: rotate(30deg);
}
.monster .right{
  transform: rotate(-30deg);
}
.burst{
  background-color:lightsteelblue;
}
</style>