<script>
export default {
  data() {
    return {
      todoId: 1,
      todoData: null,
      todosData: [],
      hide: false,
    };
  },
  methods: {
    async fetchData() {
      this.todoData = null;
      const res = await fetch(
        `https://jsonplaceholder.typicode.com/todos/${this.todoId}`
      );
      this.todoData = await res.json();
      this.todosData = [...this.todosData, this.todoData]
    },
  },
  mounted() {
    this.fetchData();
  },
  watch: {
    todoId() {
      this.fetchData();
    },
  },
};
</script>

<template>
  <p>Todo id: {{ todoId }}</p>
  <button @click="todoId++">Fetch next todo</button>
  <button @click="hide = !hide" >{{hide ? "Show Hide Todos" : "Hide Todos"}}</button>
  <p v-if="!todoData">Loading...</p>
  <ul v-else v-for="todoData in todosData">

    <li v-show= "!hide">{{ todoData }}</li>
  </ul>
</template>
