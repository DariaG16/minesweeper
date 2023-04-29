<template>
  <button @click="$emit(`tile-click`)"></button>
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
}
</style>
