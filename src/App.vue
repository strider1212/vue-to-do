<script>
let id = 0;

export default {
  data() {
    return {
      newTodo: "",
      todos: [],
      testDynamicText: "Vue To-Do List",
    };
  },
  methods: {
    addTodo() {
      this.todos.push({ id: id++, text: this.newTodo });
      this.newTodo = "";
    },
    removeTodo(todo) {
      this.todos = this.todos.filter((t) => t !== todo);
    },
  },
};
</script>

<template>
  <h1>{{ testDynamicText }}</h1>
  <form @submit.prevent="addTodo">
    <input type="text" v-model="newTodo" />
    <button>Add To-Do</button>
  </form>
  <ul>
    <li v-for="todo in todos" :key="todo.id">
      {{ todo.text }}
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
</template>

<style></style>
