<template>
  <h1 :class="{ warn: stoped }">{{ format(mm) }}</h1>
</template>

<script>
export default {
  name: "Minute",
  props: {
    mm: Number,
    stoped: Boolean,
  },
  methods: {
    format(data_num) {
      let mm = Math.floor(data_num / 60);
      return mm < 10 ? "0" + mm : "" + mm;
    },
  },
};
</script>

<style scoped>
.warn {
  color: red;
}
h1 {
  float: left;
  color: green;
}
h3 {
  margin: 40px 0 0;
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
