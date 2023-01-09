<script setup>
import HelloWorld from "./components/HelloWorld.vue";
import Todo from "./components/Todo.vue";
import Fetch from "./components/Fetch.vue";
import Works from "./components/ColorButtons.vue";
import Vmodel from "./components/Vmodel.vue";
</script>
<script>
export default {
  data() {
    return {
      childMessage: "",
      childSecondMessage: "",
      message: "hello",
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
        @responsee="(msge) => (childSecondMessage = msge)"
        msg="You did it!"
      />
      <!-- PARENTTAN CHILDA GİDEN MESAJ -->
      <div>
        {{ childMessage }}
      </div>
      {{ childSecondMessage }}
    </div>
  </header>

  <br />
  <br />
  <br />

  <div>
    <Todo> this message comes from APP Component to Todo Component with </Todo>
  </div>
  <br />
  <br />
  <br />
  <div>
    <Fetch />
  </div>
  <br />
  <br />
  <br />
  <div>
    <Works />
  </div>
  <br />

  <div><Vmodel  /></div>
</template>

<style scoped>
header {
  display: block;
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
