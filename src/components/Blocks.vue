<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
    <!-- <img width="300" src="../../src/assets/clickMe.jpg" alt="clickMe"> -->
    click Me
  </div>
</template>

<script>
export default {
    props: [ 'delay' ],
    data() {
        return {
          showBlock: false,
          timer:null, // store the start timing interval
          reactionTime:0, // set the reactionTime of click
          clickMeImg: "./assets/click-me.jpg"
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlock=true,
            this.startTimer()
        }, this.delay);

    },
    methods: {
      startTimer() {
        this.timer=setInterval(() => {
          this.reactionTime += 10
        }, 10)
      },
      stopTimer() {
        clearInterval(this.timer)
        this.$emit("end", this.reactionTime)
      }
    }
}
</script>

<style>
    .block {
    width: 300px;
    border-radius: 10px;
    background: #0faf87;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
    font-size: 30px;
  }
</style>