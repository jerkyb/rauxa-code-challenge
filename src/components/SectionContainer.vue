<template>
  <section class="container">
    <slot></slot>
  </section>
</template>

<script>
export default {
  name: "SectionContainer",
};
</script>

<style scoped lang="scss">
.container {
  border: 1px solid #2c3e50;
  border-radius: 3px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 20px;
}
</style>
