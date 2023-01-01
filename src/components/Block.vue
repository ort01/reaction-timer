<template>
  <div class="block" v-if="showBlock">Click me</div>
</template>

<script>
export default {
  name: "Block",
  props: ["delay"],
  data() {
    return {
      showBlock: false,
    };
  },
  // all the functionality inside the mounted() gets executed when the component (which has mounted() inside of its script) is mounted(loaded).
  mounted() {
    console.log("component mounted");
    setTimeout(() => {
      this.showBlock = true;
      console.log(this.delay);
    }, this.delay);
  },
  // functionality inside the updated() gets executed when the component (which has updated() inside of its script) is displayed (uptated).
  updated() {
    console.log("component updated");
  },
  // functionality inside the unmounted() gets executed when the component (which has unounted() inside of its script) is unmounted (is taken out of DOM).
  unmounted() {
    console.log("component unmounted");
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.block {
  width: 300px;
  border-radius: 20px;
  box-shadow: 1px 1px 3px 1px rgba(155, 155, 155, 0.507);
  background: #0faf87;
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>
