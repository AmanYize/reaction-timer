<template>
  <div class="Results">
    <h1>Results</h1>
    <p class="score">Reaction time: {{ score }} ms</p>
    <p class="rank">Reaction time: {{ rank }} ms</p>
  </div>
</template>

<script>
export default {
  props: ["score"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.score < 250) {
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
.Results {
  width: 400px;
  border-radius: 20px;
  background: #0faf87;
  text-align: center;
  color: white;
  padding: 100px 0;
  margin: 40px auto;
}
.score {
  font-size: 1.2em;
}
.rank {
  font-size: 1.4em;
  color: #0faf87;
  background: white;
  border-radius: 3px;
  padding: 5px 10px;
}
</style>
