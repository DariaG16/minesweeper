<template>
  <button @click.right="$emit(`right-click`)" @click="$emit(`tile-click`)">
    <h2>{{ item }}</h2>
    <h3>{{ id }}</h3>
  </button>
</template>

<script>
const props = { item: Object, id: Number };
export default {
  name: "tile",
};
</script>

<style scoped>
button {
  width: 30px;
  height: 30px;
  font-size: 10px;
}
</style>
