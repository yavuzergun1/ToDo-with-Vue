<script setup>
import HelloWorld from "./components/HelloWorld.vue";
import Todo from "./components/Todo.vue";
import Fetch from "./components/Fetch.vue";
</script>
<script>
export default {
  data() {
    return {
      childMessage: "",
    };
  },
};
</script>
<template>
  <header>
    <img
      alt="Vue logo"
      class="logo"
      src="./assets/logo.svg"
      width="125"
      height="125"
    />

    <div class="wrapper">
      <!-- @RESPONSE= CHILDDAN GELEN MESAJ -->
      <HelloWorld 
      @response="(msg) => (childMessage = msg)" 
      msg="You did it!" /> <!-- PARENTTAN CHILDA GİDEN MESAJ -->
      {{ childMessage }}
    </div>
  </header>
  <main>
    <Todo />
  </main>
  <br />
  <br />
  <br />
  <div>
    <Fetch />
  </div>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
