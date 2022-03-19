<template>
  <blink>
    <strong>Reaction Time is :{{ this.reactionTime }} Milisecond </strong>
  </blink>
</template>

<script>
export default {
  props: ["reactionTime"],

  data() {
    return {};
  },
};
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