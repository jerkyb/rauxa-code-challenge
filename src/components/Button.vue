<template>
  <button :style="{ backgroundColor: bgColor }">
    <slot>Button</slot>
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    color: {
      type: String
    }
  },
  computed: {
    bgColor() {
      return this.color;
    }
  }
};
</script>

<style scoped lang="scss">
button {
  appearance: none;
  background-color: #fff;
  border: 1px solid #2c3e50;
  border-radius: 3px;
  height: 50px;
  text-indent: -9999px;
  width: 100%;

  &:hover {
    cursor: pointer;
  }
  & + & {
    margin-left: 10px;
  }
}
</style>
