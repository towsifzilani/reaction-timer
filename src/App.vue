<template>
  <h1>Ninja Reaction Timer</h1>
  <button class="playButton" @click="start" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" />

</template>

<script>
import Block from './components/Blocks.vue'

export default {
  name: 'App',
  components: { Block },
  data() {
    return {
      isPlaying: false,
      delay: null
    }
  },
  methods: {
    start() {
      this.isPlaying = true
      this.delay = 2000 + Math.random() * 5000
    }
  }
}
</script>

<style>
body { background: url('./assets/bg.jpg') no-repeat center center}
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

h1 { color:white}
</style>
