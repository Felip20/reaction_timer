<template>
  <div class="block" v-if="showblock" @click="stopTimer">Play {{delay}}</div>
</template>

<script>
export default {
    props:['delay'],
    data(){
        return{
            showblock:false,
            score:0,
            timer:null
        }
    },
    mounted(){
        setTimeout(()=>{
            this.showblock=true;
            this.startTimer()
        },this.delay);
    },
    methods:{
        startTimer(){
            this.timer=setInterval(() => {
                this.score+=50;
            }, 50);
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
    width: 400px;
    height: 300px;
    background-color: aqua;
    margin: 20px auto;
    padding-top: 30px;
}
</style>