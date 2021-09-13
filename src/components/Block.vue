<template>
  <div v-if="showBlock" @click="stopTimer" class="box">Click me</div>
</template>

<script>
export default {
  name: "Block",
  props: ["delay"],
  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTime: 0,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
    }, this.delay);
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10;
      }, 10);
    },
    stopTimer() {
      clearInterval(this.timer);
      this.$emit("end", this.reactionTime);
    },
  },
};
</script>

<style>
.box {
  width: 320px;
  height: 320px;
  background: #2c3e50;
  border-radius: 25px;
  color: #ccc;
  margin: 24px auto;
  font-size: 22px;
  display: grid;
  place-items: center;
  cursor: pointer;
}
</style>