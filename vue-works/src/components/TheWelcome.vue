<script>
let id = 0;
export default {
  data() {
    return {
      newTodo: "",
      todos: [
        { id: id++, text: "Learn HTML", done: true },
        { id: id++, text: "Learn JavaScript", done: true },
        { id: id++, text: "Learn Vue", done: false },
      ],
    };
  },
  methods: {
    addTodo() {
      this.newTodo = this.todos.push({
        id: id++,
        text: this.newTodo,
        done: false,
      });
      this.newTodo = "";
    },
    removeTodo(todo) {
      this.todos = this.todos.filter((items) => items.id !== todo.id);
    },
  },
};
</script>

<template>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo" />
    <button>Add Todo</button>
  </form>
  <ul>
    <li v-for="todo in todos" :key="todo.id">
      <input type="checkbox" v-model="todo.done" />
      <span :class="{done: todo.done}">
        {{ todo.text }}
      </span>
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
</template>

<style>
.done {
  text-decoration: line-through;
}
</style>
