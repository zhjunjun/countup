<template>
  <h1 :class="{ warn: stoped }">{{ format }}</h1>
</template>

<script>
export default {
  name: "Second",
  data() {
    return {};
  },
  props: {
    ss: Number,
    stoped: Boolean,
  },
  methods: {},
  computed: {
    format() {
      let ss = this.ss % 60;
      return ss < 10 ? "0" + ss : "" + ss;
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
