<template>
  <h1>How fast can you press the box?</h1>
  <p class="instructions" v-if="instructionsVisible">Hit play and wait for the box to appear</p>
  <button id="button" @click='start' :disabled='isPlaying'>{{buttonText}}</button>
  <theBlock v-if="isPlaying" :delay='delay' @end='endGame'/>
  <TheResults v-if="showResults" :score="score"/>
  <TheLevels v-if="showResults"/>
  
</template>

<script>
import TheBlock from './components/theBlock.vue'
import TheResults from './components/theResults.vue'
import TheLevels from './components/theLevels.vue'

export default {
  name: 'App',
  components: {
    TheBlock,
    TheResults,
    TheLevels
  },
  data () {
    return{
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false,
      buttonText: 'Play',
      instructionsVisible: true
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      this.score = null
      this.showResults = false
      this.instructionsVisible = false
    },
    endGame(reactionTime){
      this.score = reactionTime
      this.isPlaying = false
      this.showResults =true
      this.buttonText = 'Try again'
    }
  }
}
</script>

<style>
 @import url('https://fonts.googleapis.com/css2?family=Poppins&family=Source+Code+Pro&display=swap');


#app {
  font-family: 'Poppins', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
button {
  padding:20px 40px;
  font-size: 20px;
  color: white;
  background: #0faf87;
  border: none;
  border-radius: 10px;
  box-shadow: 2.5px 5px 18px #888888;
  cursor: pointer;
}
button[disabled]{
  opacity: 0.5;
  cursor: not-allowed;
}
h1{
  padding: 20px;
  margin-bottom: 30px;
}
.instructions{
  font-size: 20px;
  margin-bottom: 20px;
}
</style>
