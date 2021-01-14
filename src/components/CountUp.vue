<template>
  <div id="count_up">
    <Minute :mm="second" :stoped="stoped" />
    <div id="quote">:</div>
    <Second :ss="second" :stoped="stoped" />
    <div id="btn_control">
      <button @click="stop()">暂停</button>
      <button @click="start()">继续</button>
    </div>
  </div>
</template>

<script>
import Minute from "./Minute.vue";
import Second from "./Second.vue";

export default {
  name: "CountUp",
  components: {
    Minute,
    Second,
  },
  methods: {
    stop() {
      console.log("stop");
      if (this.stoped === true) {
        return;
      }
      this.stoped = true;
      clearInterval(this.timer);
    },
    start() {
      console.log("start");
      if (this.stoped === false) {
        return;
      }
      this.stoped = false;
      this.init_timer();
    },
    init_timer() {
      this.timer = setInterval(() => {
        this.second += 1;
      }, 1000);
    },
  },
  created() {
    this.init_timer();
  },
  data() {
    return {
      second: 0, // 时间
      stoped: false, // 启停状态
      timer: null, // 计时器
    };
  },
};
</script>

<style scoped>
#count_up {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding-left: 14px;
  padding-top: 10px;
  height: 100px;
  width: 100px;
  border: 0.9px solid;
  display: inline-block;
  margin-left: 20px;
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
  float: left;
}
</style>