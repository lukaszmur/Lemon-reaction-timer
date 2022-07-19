<template>
  <p>Reaction time - {{score}} ms</p>
  <p class="rank">{{rank}}</p>
</template>

<script>
export default {
    props: ['score'],
    data() {
      return {
        rank:null
      }
    },
    mounted() {
      if (this.score < 200) {
        this.rank = 'Good reflexes!'
      } else if (this.score < 400) {
        this.rank = 'Average time, try again'
      } else {
        this.rank = 'You are weak, You have to practice...'
      }
      }
    }


</script>

<style>
.rank {
  font-size: 1.4em;
  color: #a4af0f;
  font-weight: bold;
}

</style>