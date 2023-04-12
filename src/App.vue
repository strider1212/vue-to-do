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
      this.todos.push({ id: id++, text: this.newTodo, done: false });
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
      <input type="checkbox" v-model="todo.done" />
      <span :class="{ done: todo.done }">{{ todo.text }}</span>
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
</template>

<style>
.done {
  text-decoration: line-through;
}
</style>
