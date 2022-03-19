<template>
  <blink>
    <strong>Reaction Time is :{{ this.reactionTime }} Milisecond </strong>
    <br />
    <strong>{{ this.rank }} </strong>
  </blink>
</template>

<script>
export default {
  props: ['reactionTime'],

  data() {
    return {
      rank:''
    }
  },
  mounted(){ 
    switch(true)
    {
      case(this.reactionTime < 1000)
              : this.rank = 'Wow !!! Ninja Fingers you have'
                break
      case(this.reactionTime < 2000)
              : this.rank = 'Good  !!! Fast speed'
                break
                
      case(this.reactionTime < 3000)
              : this.rank = 'Boaring   !!! you are slow as sneel'
                break
      default          
       : this.rank = 'Getout  fucking boaring'
                break
                

    }
  }
}
</script>

<style>
strong {
  color: brown;
  text-decoration: underline;
  font-style: italic;
  font-size: 15px;
  font-weight: bold;

  animation: blinking 1.5s infinite;
  font-size: 20px;
}
@keyframes blinking {
  0% {
    color: red;
  }
  47% {
    color: #000;
  }
  62% {
    color: transparent;
  }
  97% {
    color: transparent;
  }
  100% {
    color: #000;
  }
}
</style>