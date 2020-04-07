<template>
  <SectionContainer>
    <h2>Scene Configuration</h2>
    <ButtonGroup>
      <Button>Color</Button>
      <Button>Color</Button>
      <Button>Color</Button>
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
    Button
  }
};
</script>

<style scoped lang="scss">
h2 {
  font-size: 16px;
}
</style>
