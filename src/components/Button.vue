<template>
  <button><slot>Button</slot></button>
</template>

<script>
export default {
  name: "Button"
};
</script>

<style scoped lang="scss">
button {
  appearance: none;
  background-color: #fff;
  border: 1px solid #2c3e50;
  height: 50px;
  width: 100%;
}
</style>
