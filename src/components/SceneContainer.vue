<template>
  <SectionContainer>
    <h1>Awesome 3D Scene</h1>
    <SceneCanvas />
  </SectionContainer>
</template>

<script>
import SectionContainer from "./SectionContainer";
import SceneCanvas from "./SceneCanvas";

export default {
  name: "SceneContainer",
  components: {
    SectionContainer,
    SceneCanvas
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h1 {
  font-size: 24px;
}
</style>
