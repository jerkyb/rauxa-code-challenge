<template>
  <section id="app">
    <SceneContainer />
    <SceneConfigurator />
  </section>
</template>

<script>
import SceneContainer from "./components/SceneContainer.vue";
import SceneConfigurator from "./components/SceneConfigurator";

export default {
  name: "App",
  components: {
    SceneContainer,
    SceneConfigurator
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
  margin-top: 60px;
}
</style>
