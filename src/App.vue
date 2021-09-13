<template>
  <h1 class="title">Reaction Timer</h1>
  <button class="playBtn" @click="play" :disabled="isPlaying">play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <Results v-if="showResults" :score="score" />
</template>

<script>
import Block from "./components/Block";
import Results from "./components/Results";

export default {
  name: "App",
  components: {
    Block,
    Results,
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false,
    };
  },
  methods: {
    play() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      this.showResults = false;
    },
    endGame(time) {
      this.score = time;
      this.isPlaying = false;
      this.showResults = true;
    },
  },
};
</script>

<style>
.title {
  margin-bottom: 18px;
}
.playBtn {
  background: #2c3e50;
  color: #ccc;
  padding: 8px 12px;
  font-size: 17px;
  border-radius: 8px;
  border: none;
  cursor: pointer;
  margin-bottom: 25px;
}
.playBtn:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}
</style>
