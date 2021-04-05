<template>
  <div id="demo">
      <lottie :options="defaultOptions" :height="400" :width="400" v-on:animCreated="handleAnimation"/>
      <div>
          <p>Speed: x{{animationSpeed}}</p>
          <input type="range" value="1" min="0" max="3" step="0.5"
                  v-on:change="onSpeedChange" v-model="animationSpeed">
      </div>
      <button v-on:click="stop">stop</button>
      <button v-on:click="pause">pause</button>
      <button v-on:click="play">play</button>
  </div>
</template>

<script>
import Lottie from './Lottie';

export default {
  name: 'demo',
  components: {
    'lottie': Lottie
  },
  data() {
    return {
      defaultOptions: {
        path : '/lottie-data/demo.json'
      },
      animationSpeed: 1
    }
  },
  methods: {
    handleAnimation: function (anim) {
      this.anim = anim;
    },
    stop: function () {
      this.anim.stop();
    },
    play: function () {
      this.anim.play();
    },
    pause: function () {
      this.anim.pause();
    },
    onSpeedChange: function () {
      this.anim.setSpeed(this.animationSpeed);
    }
  }
}
</script>

<style>
#demo {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>