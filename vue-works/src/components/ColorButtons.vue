<script>
export default {
  data() {
    return {
      colors: ["red", "blue", "pink"],
      red: false,
      blue: true,
      pink: false,
    };
  },
  methods: {
    makeRed() {
      this.red = true;
      this.blue = false;
      this.pink = false;
    },
    makeBlue() {
      this.red = false;
      this.blue = true;
      this.pink = false;
    },
    makePink() {
      this.red = false;
      this.blue = false;
      this.pink = true;
    },
  },
};
</script>

<template>
  <div>
    <button @click="makeRed">RED</button>
    <button @click="makeBlue">BLUE</button>
    <button @click="makePink">PINK</button>
  </div>

  <!-- DEĞİŞKEN CLASS YAPISI HEM DİZİ İÇİNDE HEM DE OBJECT İÇİNDE AŞAĞIDAKİ ŞEKİLDE YAPILABİLİR. -->

  <div  style="display: flex">
    <div
      style="width: 100px; height: 100px; margin-top: 20px; margin-right: 25px;"
      :class="[red ? 'red' : blue ? 'blue' : pink ? 'pink' : null]"
    ></div>

    <div
      style="width: 100px; height: 100px; margin-top: 20px"
      :class="[
        {
          red: red,
          blue: blue,
          pink: pink,
        },
      ]"
    ></div>
  </div>
</template>

<style scoped>
.blue {
  background-color: blue;
}
.red {
  background-color: red;
}
.pink {
  background-color: pink;
}
</style>
