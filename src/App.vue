<script>
let id = 0;

export default {
  data() {
    return {
      todos: [{ id: id++, text: "test text" }],
      testDynamicText: "Vue To-Do List",
    };
  },
  methods: {},
};
</script>

<template>
  <h1>{{ testDynamicText }}</h1>
  <ul>
    <li v-for="todo in todos" :key="todo.id">
      {{ todo.text }}
    </li>
  </ul>
</template>

<style></style>
