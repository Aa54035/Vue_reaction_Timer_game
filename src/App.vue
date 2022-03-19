<template>
  <h1>Hello App Vue JS , This is Random Number Genrator !!!</h1>
  <!-- <button type="button" @click="playGame" :disabled="showGame" class="btn btn-primary">Play </button> -->
  <button type="button" @click="playGame" class="btn btn-primary">Play</button>

  <BlockItem v-if="showGame" :delay="delay" @endOfTheGame="endOfTheGame" />
  <br/>

  <ResultsItem v-if="showResults"  :reactionTime="this.reactionTime" /> 
  
</template>

<script>
import BlockItem from './components/BlockItem.vue'
import ResultsItem from './components/ResultsItem.vue'

export default {
  name: 'App' ,
  components: { BlockItem ,ResultsItem},
  data() {
    return {
      showGame: false,
      delay: null,
      reactionTime: 0,
      showResults: false,
    };
  },
  methods: {
    endOfTheGame(reactionTime) {
      this.reactionTime = reactionTime;
      this.showGame = false;
      this.showResults = true;
    },
    playGame() {
      this.delay = 2000 + Math.random() * 5000;
      this.showGame = true;
      this.showResults = false;

      this.reactionTime = 0;
      console.log('The Delay is ' + this.delay);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
