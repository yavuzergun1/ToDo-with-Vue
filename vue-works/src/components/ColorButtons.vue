<script>
export default {
  data() {
    return {
      red: false,
      blue: true,
      pink: false,
      className: "red",
    };
  },

  methods: {
    // UZUN YÖNTEM
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
    // KISA VE PRATİK YÖNTEM
    setColor(color) {
      this.className = color;
      console.log(color);
    },
  },
};
</script>

<template>
  <h1>Buttons and conditional rendering</h1>
  <div>
    <button @click="makeRed">RED</button>
    <button @click="makeBlue">BLUE</button>
    <button @click="makePink">PINK</button>
  </div>

  <!-- DEĞİŞKEN CLASS YAPISI HEM DİZİ İÇİNDE HEM DE OBJECT İÇİNDE AŞAĞIDAKİ ŞEKİLDE YAPILABİLİR. -->

  <div style="display: flex">
    <div
      style="width: 100px; height: 100px; margin-top: 20px; margin-right: 25px"
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

  <div>
    <div style="margin-top: 25px">
      <button @click="setColor('red')">RED</button>
      <button @click="setColor('blue')">BLUE</button>
      <button @click="setColor('pink')">PINK</button>
    </div>

    <div
      style="width: 100px; height: 100px; margin-top: 20px"
      :class="className"
    ></div>
  </div>
  <form >
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
  </form>
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
