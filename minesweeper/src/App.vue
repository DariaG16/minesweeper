<script setup>
import HelloWorld from "./components/HelloWorld.vue";
import TheWelcome from "./components/TheWelcome.vue";
import tile from "./components/tile.vue";
import startBtn from "./components/startBtn.vue";
</script>

<template>
  <body>
    <header><h1>Minesweeper</h1></header>
    <div v-on:contextmenu.prevent>
      <button
        id="startBtn"
        v-if="!hidden"
        v-on:click="hidden = true"
        @click="makeTiles(2)"
      >
        NEW GAME
      </button>
      <tile
        @right-click="flag"
        @tile-click="reveal"
        v-for="item in items"
        :key="item"
        v-if="!revealed"
        v-on:click="revealed = true"
        :style="{
          backgroundColor: flagged ? 'red' : 'white',
        }"
        >{{ item.help }}</tile
      >
    </div>
  </body>
</template>

<script>
export default {
  name: "minesweeper",
  components: { tile },
  data() {
    return {
      hidden: false,
      revealed: false,
      flagged: false,
      items: [],
    };
  },
  methods: {
    makeTiles: function (max) {
      for (let i = 0; i < 588; i++) {
        this.items.push(`help: ${Math.floor(Math.random() * max)}`);
      }
      console.log(this.items);
    },
    reveal: function () {
      console.log("revealed");
      //check if there is a bomb
      //if there is: function gameover
      //if there isn't: remove btn
    },
    flag: function () {
      console.log("flagged");
    },
  },
};
</script>

<style scoped>
#startBtn {
  padding: 50px;
  font-size: 50px;
  margin: 25%;
  background-color: #ff9770;
  /* border: solid #ff70a6 5px; */
  color: #e9ff70;
  cursor: pointer;
}
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
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-content: center;
}
</style>
