<template>
 <div class="item">
  <div class="block" v-if="showBlock" @click="stopTimer">
  </div>
</div>
</template>

<script>
export default {
  props: ['delay'],
  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTime: 0
    }
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true
      this.startTimer()
    }, this.delay)
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10
      }, 10)
    },
    stopTimer() {
      clearInterval(this.timer)
      this.$emit('end', this.reactionTime)
    }
  }

}
</script>

<style>
.block {
  padding: 40px;
  width: 5.1em;
  height: 5.1em;
  margin-left: 120px;
  margin-top: 40px;
  background-color: #ffe135;
  border-radius: 50% 15%;
  box-shadow: inset 0.4em 0.4em  #ccb42a;
  transform: rotate(225deg);
  position: absolute;

}
.item
{
  width:400px;
  position: relative;
  margin: auto;
  }
</style>