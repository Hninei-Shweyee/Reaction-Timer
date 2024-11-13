<template>
  <div class="block" v-if="showblock" @click="stopTimer">Click here {{delay}}</div>
  
</template>

<script>
export default {
    props:['delay'],
    data(){
      return {
        showblock:false,
        score:0,
        timer:null
      }
    },
    mounted(){
      setTimeout(()=>{
        this.showblock=true;
        this.startTImer()

      },this.delay);
      

    },
    methods:{
      startTImer(){
        this.timer=setInterval(()=>{
          this.score+=50;
        },50);
      },
      stopTimer(){
        clearInterval(this.timer);
        this.$emit("endGame",this.score)
      }
    }
}
</script>

<style>
.block{
    background-color: aqua;
    width: 400px;
    height: 200px;
    margin: 20px auto;
    padding-top: 30px;
}
</style>