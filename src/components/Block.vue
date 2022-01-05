<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
      click me
  </div>
</template>

<script>
import { TransitionGroup } from '@vue/runtime-dom'
export default {
    props: ['delay'],
    data() {
        return {
            showBlock: false,
            timer: null,
            rectionTime: 0
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlock = true
            this.startTimer()
        },this.delay)
    },
    methods: {
        startTimer() {
            this.timer = setInterval(() => {
                this.rectionTime += 10
            }, 10);
        },
        stopTimer() {
            clearInterval(this.timer)
            this.$emit('end',this.rectionTime)
        }
    }
}
</script>

<style>
.block {
    width: 400px;
    border-radius: 20px;
    background: #7111df;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
}

</style>