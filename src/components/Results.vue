<template>
  <p>
    Your reaction time is <span class="score">{{ score }}</span> ms
  </p>
  <p class="rank">{{ rank }}</p>
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
    if (this.score < 250) {
      this.rank = "Ninja Fingers";
    } else if (this.score < 400) {
      this.rank = "Rapid Reflexes";
    } else {
      this.rank = "Snail pace...";
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
p {
  font-size: 1.25rem;
}
.score {
  font-weight: 900;
  color: #0faf87;
}
.rank {
  font-size: 1rem;
  color: #0faf87;
  letter-spacing: 3px;
}
</style>
