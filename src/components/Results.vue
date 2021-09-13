<template>
  <p>result : {{ score }} - ms</p>
  <p>{{ rank }}</p>
</template>

<script>
export default {
  name: "Results",
  props: ["score"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.score < 200) {
      this.rank = "Ninja Fingers";
    } else if (this.score < 400) {
      this.rank = "Rapid Reflexes";
    } else {
      this.rank = "Snail Pace...";
    }
  },
};
</script>

<style>
</style>