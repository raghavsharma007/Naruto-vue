<template>
  <div class="bg-blue-400 h-screen text-center">
    <h1 class="text-3xl header-title bg-blue-900 w-1/3 m-auto text-center p-2 text-blue-200 rounded-md">Ninjustu Finish Timer</h1>
    <button @click="start" :disabled="isPlaying" class="bg-gray-300 focus:outline-none uppercase p-2 text-xl font-semibold rounded-lg w-1/12 mt-4">play</button>
    <Block v-if="isPlaying" :delay="delay" @end="endGame" />
    <Result v-if="showResults" :score="score" />
  </div>
</template>

<script>
import Block from './components/Block.vue'
import Result from './components/Result.vue'

export default {
  name: 'App',
  components: { Block, Result },
  data(){
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false
    }
  },
  methods: {
    start() {
        this.delay = 2000 + Math.random() * 5000;
        this.isPlaying = true
        this.showResults = false
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false
      this.showResults = true
    }
  }
}
</script>


<style scoped>
@import url('https://fonts.googleapis.com/css2?family=RocknRoll+One&display=swap');

.header-title {
  font-family: 'RocknRoll One', sans-serif;
}

</style>
