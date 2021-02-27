<template>
<p>Lets see how quick you can react👇🏻</p>
  <h1>Awesome Reaction Timer</h1>
  <button class="init" @click="start" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <Result v-if="showResult" :score="score"/>
</template>

<script>
import Block from "./components/Block.vue";
import Result from "./components/Result.vue";

export default {
  name: "App",
  components: { Block, Result },

  data() {
    return {
      isPlaying: false,
      delay: null,
      score : null,
      showResult : false,
    };
  },

  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      this.showResult = false
    },
    endGame(rt){
      this.score = rt
      this.isPlaying = false
      this.showResult= true
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
.init{
  background: rgb(4, 255, 129);
  border: 0;
  padding: 15px 30px;
  font-size: 18px;
  border-radius: 10px;
}
.init:disabled{
  cursor: not-allowed;
}
</style>
