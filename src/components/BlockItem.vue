
<template>
  <div class="block" v-if="showBlocks" @click="stopTimer">
    Click Me user :)
    <strong>{{ this.delay }}</strong>
  </div>
</template>

<script>
export default {
  props: ['delay'],
  data() {
    return {
      showBlocks: false,
      delay1: this.delay,
      startTime: null,
      endTime: null,
      showStrong:false
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlocks = true;
      console.log("components has been mointed in Block " + this.delay);

      this.startTimer();
    }, this.delay);
  },
  updated() {
    console.log("components has been updated " + this.delay);
  },
  unmounted() {
    console.log("components has been unmounted " + this.delay);
  },
  methods: {
    startTimer() {
      this.startTime = setInterval(() => {
        this.endTime += 10;
      }, 10);
    },
    stopTimer() {
      clearInterval(this.startTime);
            console.log("Reaction timer of user " + this.endTime);
            this.$emit('endOfTheGame',this.endTime)

    },
  },
};
</script>

<style>
.block {
  width: 400px;
  border-radius: 20px;
  background: yellowgreen;
  color: rgb(25, 33, 41);
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;

  border: 5px solid black;
  font-family: Arial, Helvetica, sans-serif;
  text-decoration: underline;
}
</style>