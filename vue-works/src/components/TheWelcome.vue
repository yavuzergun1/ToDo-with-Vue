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
<div v-for="numbers in sets">
  {{ numbers }}
  <div v-for="n in even(numbers)">{{ n }}</div>
</div>
</template>
