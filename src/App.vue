<template>
  <h1>Reaction Timer</h1>
  <button class="play-button" @click="start" :disabled="isPlaying">Play</button>
  <button class="reset-button" @click="reset">Reset</button>
  <Block v-if="isPlaying" :delay="delay" />
</template>

<script>
import Block from "./components/Block.vue";

export default {
  name: "App",
  components: {
    Block,
  },
  data: () => {
    return {
      isPlaying: false,
      delay: null,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
    },
    reset() {
      this.isPlaying = false;
    },
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
.play-button,
.reset-button {
  background: none;
  text-transform: uppercase;
  letter-spacing: 3px;
  border: 2px solid rgba(21, 121, 59, 0.493);
  border-radius: 5px;
  padding: 10px 20px;
  margin: 10px 20px;
  font-size: 18px;
  font-weight: 600;
  font-family: inherit;
  color: #0faf87;
  box-shadow: 1px 1px 3px 1px rgba(155, 155, 155, 0.507);
  cursor: pointer;
  position: relative;
  overflow: hidden;
  transition: all 0.5s;
}
.play-button:before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 0%;
  background-color: #0faf87;
  z-index: -1;
  border-radius: 0% 0% 50% 50%;
  transition: all 0.5s;
}

.play-button:hover,
.reset-button:hover {
  color: white;
}
.play-button:hover:before,
.reset-button:hover:before {
  height: 200%;
}
.play-button:disabled {
  color: rgba(68, 68, 68, 0.301);
  border: 2px solid rgba(68, 68, 68, 0.301);
}
.play-button:disabled:before {
  background: none;
}

.reset-button {
  color: rgb(156, 67, 67);
  border: 2px solid rgba(170, 53, 53, 0.493);
}
.reset-button:before {
  border-radius: 50% 50% 0% 0%;
  background-color: rgb(156, 67, 67);
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 0%;
  z-index: -1;
  transition: all 0.5s;
}
</style>
