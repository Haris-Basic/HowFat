<template>
  <h2>Your result is {{ score }} ms</h2>
  <p>{{ rank }}</p>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            rank: null
        }
    },
    mounted() {
        if(this.score < 250) {
            this.rank = 'Exelent'
        } else if(this.score < 450) {
            this.rank = 'Good'
        } else if(this.score < 650) {
            this.rank = 'That can be better'
        } else if(this.score < 850) {
            this.rank = 'OMG'
        } else {
            this.rank = 'Go home'
        }
    }
}
</script>

<style>
.rank {
    font-size: 1.5em;
    color: white;
    font-weight: bold;
}
</style>