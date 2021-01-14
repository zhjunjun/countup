<template>
  <div id="app">
    <CountUp />
    <CountUp />
  </div>
</template>

<script>
import CountUp from "./components/CountUp";

export default {
  name: "App",
  components: {
    CountUp,
  },
  methods: {},
  created() {
    this.init_timer();
  },
  data() {
    return {};
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
h1 {
  float: left;
  margin: auto;
}
#quote {
  float: left;
  hight: 12px;
  font-size: 28px;
  font-style: bold;
  margin: 80px, 0px;
}
#btn_control {
  margin-top: 10px;
  clear: both;
  float: left;
}
</style>