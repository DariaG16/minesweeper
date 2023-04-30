<template>
  <button @click.right="$emit(`right-click`)" @click="$emit(`tile-click`)">
    <slot></slot>
  </button>
</template>

<script>
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
