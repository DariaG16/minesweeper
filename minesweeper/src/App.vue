<script setup>
import HelloWorld from "./components/HelloWorld.vue";
import TheWelcome from "./components/TheWelcome.vue";
import tile from "./components/tile.vue";
import startBtn from "./components/startBtn.vue";
</script>

<template>
  <body>
    <header><h1>Minesweeper</h1></header>
    <div>
      <startBtn @start-click="makeTiles">NEW GAME</startBtn>
      <tile @tile-click="reveal" v-for="item in items" :key="item"></tile>
    </div>
  </body>
</template>

<script>
export default {
  name: "minesweeper",
  components: { tile },
  data() {
    return {
      items: [],
      methods: {
        makeTiles: function () {
          for (let i = 0; i < 20; i++) {
            this.items.push(Math.random());
          }
          console.log(this.items);
        },
        reveal: function () {
          //check if there is a bomb
          //if there is: function gameover
          //if there isn't: remove btn
        },
      },
    };
  },
};
</script>

<style scoped>
h1 {
  background-color: #ff9770;
  font-size: 60px;
  text-align: center;
  margin: 50px auto;
  margin-top: 50px;
  color: #ff70a6;
  width: 600px;
  text-shadow: 3px 1px #63458a;
  border: solid #e9ff70 5px;
}
div {
  background-color: #ffd670;
  width: 650px;
  height: 80vh;
  margin: 30px auto;
  border: solid #e9ff70 5px;
}
</style>
