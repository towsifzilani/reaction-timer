<template>
  <h1>Ninja Reaction Timer</h1>
  <button class="playButton" @click="start" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <Results v-if="showResults" :score="score" />

</template>

<script>
import Block from './components/Blocks.vue'
import Results from './components/Results.vue'

export default {
  name: 'App',
  components: { Block, Results },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: 0,
      showResults:false
    }
  },
  methods: {
    start() {
      this.isPlaying = true
      this.delay = 2000 + Math.random() * 5000
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false,
      this.showResults=true
    }
  }
}
</script>

<style>
/* body { background: url('./assets/bg.jpg') no-repeat center center} */
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}

.playButton {
  padding:10px 20px;
  cursor: pointer;
  border:none;
}
.playButton:hover { 
  background: #6777ef;
  color: white;
  border:none;
}

/* h1 { color:white} */
</style>
