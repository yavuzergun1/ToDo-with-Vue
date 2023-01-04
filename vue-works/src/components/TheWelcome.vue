<script>
let id = 0;
export default {

  data() {
    return {
      sets: [[1, 2, 3, 4, 5], [6, 7, 8, 9, 10]]
    }
  },
  methods: {
    even(numbers) {
      return numbers.filter(number => number % 2 === 0)
    }
  }
}
</script>

<template>
  <form @submit="add">
    <input type="text" />
  </form>
<ul v-for="numbers in sets">
  {{ numbers }}
  <li v-for="n in even(numbers)">{{ n }}</li>
</ul>
</template>
