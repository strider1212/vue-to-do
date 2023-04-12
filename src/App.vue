<script>
export default {
  data() {
    return {
      testState: "testing",
    };
  },
  methods: {
    test() {
      console.log(this.testState);
    },
  },
};
</script>

<template>
  <h1>Vue To-Do List</h1>
  <button @click="test">test</button>
</template>

<style></style>
