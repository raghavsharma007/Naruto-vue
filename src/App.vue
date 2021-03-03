<template>
  <h1 class="text-3xl header-title">Ninjustu Finish Timer</h1>
  <button @click="start" :disabled="isPlaying" class="bg-gray-300 focus:outline-none">play</button>
  <Block v-if="isPlaying" :delay="delay" />
</template>

<script>
import Block from './components/Block.vue'

export default {
  name: 'App',
  components: { Block },
  data(){
    return {
      isPlaying: false,
      delay: null
    }
  },
  methods: {
    start() {
        this.delay = 2000 + Math.random() * 5000;
        this.isPlaying = true;
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
