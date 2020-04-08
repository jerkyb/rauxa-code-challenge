<template>
  <SectionContainer>
    <h2>Scene Color and Texture Configuration</h2>
    <ButtonGroup>
      <Button
        v-for="(color, index) in colors"
        :key="index"
        :color="color.hex"
        >{{ color.label }}</Button
      >
    </ButtonGroup>
    <ButtonGroup>
      <Button>Texture</Button>
    </ButtonGroup>
  </SectionContainer>
</template>

<script>
import SectionContainer from "./SectionContainer";
import ButtonGroup from "./ButtonGroup";
import Button from "./Button";

export default {
  name: "SceneConfigurator",
  components: {
    SectionContainer,
    ButtonGroup,
    Button,
  },
  props: {
    colors: {
      type: Array,
    },
  },
};
</script>

<style scoped lang="scss">
h2 {
  font-size: 16px;
}
</style>
