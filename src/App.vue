<script>
let id = 0;

export default {
  data() {
    return {
      newTodo: "test",
      todos: [{ id: id++, text: "test text" }],
      testDynamicText: "Vue To-Do List",
    };
  },
  methods: {
    addTodo() {
      this.todos.push({ id: id++, text: this.newTodo });
    },
  },
};
</script>

<template>
  <h1>{{ testDynamicText }}</h1>
  <form @submit.prevent="addTodo">
    <button>Add To-Do</button>
  </form>
  <ul>
    <li v-for="todo in todos" :key="todo.id">
      {{ todo.text }}
    </li>
  </ul>
</template>

<style></style>
