<script setup></script>
<template>
  <button @click="$emit(`note-click`)"><slot></slot></button>
</template>

<script>
export default {
  name: "startBtn",
};
</script>

<style scoped>
button {
  padding: 50px;
  font-size: 50px;
  margin: 25%;
  background-color: #ff9770;
  border: solid #ff70a6 5px;
  color: #e9ff70;
  cursor: pointer;
}
</style>
