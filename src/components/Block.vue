<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
      CLICK!
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
           this.timer = setInterval (() => {
               this.reactionTime += 10
           }, 10)
        },
        stopTimer() {
          clearInterval(this.timer)
          this.$emit('end', this.reactionTime)
        //   console.log(this.reactionTime)
        }
    }

}
</script>

<style>
.block {
     width: 400px;
     border-radius: 20px;
     background: rgb(0, 172, 106);
     color: white;
    text-align: center;
    padding: 100px 0;
   margin: 40px auto;
}
</style>