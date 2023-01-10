<script>
export default {
  data() {
    return {
      firstMessage: "",
      secondMessage: "",
      thirdMessage: "",
      fourthMessage: "",
    };
  },
};
</script>

<template>
  <!-- LAZY İLE ENTERA BASINCA ÇALIŞIR -->
  <div
    class="flex"
    style="display: flex; justify-content: space-around; margin: 20px 0px"
  >
    <div>
      <input v-model="firstMessage" placeholder="v-model" />
      <div>{{ firstMessage }}</div>
    </div>
    <div>
      <input v-model.lazy="secondMessage" placeholder="v-model-lazy" />
      <div>{{ secondMessage }}</div>
    </div>

    <div>
      <input
        @keyup="thirdMessage = $event.target.value"
        placeholder="with event target"
      />
      <div>{{ thirdMessage }}</div>
    </div>
    <div>
      <input
        @keyup.space="fourthMessage = $event.target.value"
        placeholder="keyup space"
      />
      <div>{{ fourthMessage }}</div>
    </div>
  </div>
</template>
