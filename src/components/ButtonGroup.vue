<template>
  <div class="buttons">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "ButtonGroup"
};
</script>

<style scoped lang="scss">
.buttons {
  display: flex;
  justify-content: space-between;
  margin: 0 0 20px;
}
</style>
