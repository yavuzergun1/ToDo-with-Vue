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
  <!-- LAZY İLE ENTERA BASINCA ÇALIŞIR -->
  <input v-model.lazy="message" />
  <div>{{ message }}</div>
</template>
