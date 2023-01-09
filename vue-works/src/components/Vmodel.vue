<script>
export default {
  data() {
    return {
      message: "",
    };
  },
};
</script>

<template>
  <input v-model="message" />
  <div>{{ message }}</div>
</template>
