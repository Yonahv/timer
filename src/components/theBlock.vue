<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
    Click me FAST!
  </div>
</template>

<script>
export default {
    props: ['delay'],
    data () {
      return{
      showBlock: false,
      timer: null,
      reactionTime: 0
      }
    },
    mounted() {
      setTimeout (()=>{
        this.showBlock = true
        this.startTimer()
      },this.delay)
    },
    methods: {
      startTimer () {
        this.timer = setInterval(() => {
          this.reactionTime += 10
        },10);
          
        }, 
      
      stopTimer () {
        clearInterval(this.timer)
        this.$emit('end', this.reactionTime)
      }
    }
}
</script>

<style>
.block{
  width: 400px;
  border-radius: 20px;
  background: #fcff31;
  text-align: center;
  margin: 40px auto;
  padding: 80px 0;
  font-size: 40px;
  color: rgb(0, 0, 0);
  cursor: pointer;
}
</style>