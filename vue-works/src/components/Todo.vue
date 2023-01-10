<script>
let id = 0;
export default {
  data() {
    return {
      newTodo: "",
      todos: [{ id: id++, text: "Learn HTML", done: true, priority: true }],
      hide: false,
      hideAll: false,
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
  computed: {
    hidetodos() {
      return this.hide ? this.todos.filter((todo) => !todo.done) : this.todos;
    },
  },
};
</script>

<template>
  <!-- THIS SLOT COMES FROM APP COMPONENT  -->
  <slot />
  <h1>ToDo</h1>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo" />
    <button>Add Todo</button>
  </form>
  <ul>
    <li v-for="todo in hidetodos" :key="todo.id" v-if="!hideAll">
      <input type="checkbox" v-model="todo.done" />
      <span
        :class="{ done: todo.done, priority: todo.priority }"
        class="static-class"
      >
        {{ todo.text }}
      </span>
      <button @click="removeTodo(todo)">X</button>
      <button @click="todo.priority = !todo.priority">Priority</button>
    </li>
    <button @click="hide = !hide">
      {{ hide ? "show completed" : "hide completed" }}
    </button>
    <button @click="hideAll = !hideAll">
      {{ hideAll ? "show all" : "hide all" }}
    </button>
  </ul>
</template>

<style>
.done {
  text-decoration: line-through;
}
.priority {
  color: red;
}
</style>
