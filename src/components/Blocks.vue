<template>
  <div class="block" v-if="showBlock">
    Click Me
  </div>
</template>

<script>
export default {
    props: [ 'delay' ],
    data() {
        return {
            showBlock: false
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlock=true
        }, this.delay);

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