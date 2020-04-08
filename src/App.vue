<template>
  <section id="app">
    <SceneContainer />
  </section>
</template>

<script>
import SceneContainer from "./components/SceneContainer";

export default {
  name: "App",
  components: {
    SceneContainer
  }
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 60px auto 0 auto;
}
</style>
