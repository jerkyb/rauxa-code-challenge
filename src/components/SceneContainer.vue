<template>
  <SectionContainer>
    <h1>ThreeJs Scene</h1>
    <canvas id="canvas" ref="canvas"></canvas>
    <SceneConfigurator
      :colors="colors"
      @onColorChange="updateMaterialColor($event)"
    />
  </SectionContainer>
</template>

<script>
import * as THREE from "three";
import { GLTFLoader } from "three/examples/jsm/loaders/GLTFLoader.js";
import SectionContainer from "./SectionContainer";
import SceneConfigurator from "./SceneConfigurator";

export default {
  name: "SceneContainer",
  components: {
    SectionContainer,
    SceneConfigurator,
  },
  data() {
    return {
      colors: [
        {
          label: "Green",
          hex: "#00ff00",
        },
        {
          label: "Red",
          hex: "#8e1600",
        },
        {
          label: "Blue",
          hex: "#bfe6ff",
        },
      ],
      cube: null,
      material: null,
      renderer: null,
      scene: null,
      camera: null,
    };
  },
  methods: {
    init3DScene: function() {
      this.scene = new THREE.Scene();
      this.scene.background = new THREE.Color("#b3b3bc");
      this.gltfLoader = new GLTFLoader();
      this.gltfLoader.load("/gltf/scene.gltf", (gltf) => {
        let shoe = gltf.scene.children[0];
        shoe.position.x = -2;
        shoe.rotation.x = 15;
        shoe.rotation.y = 9;
        shoe.scale.set(0.5, 0.5, 0.5);
        this.scene.add(gltf.scene);
      });
      const cameraConfig = [
        75,
        this.$refs.canvas.clientWidth / this.$refs.canvas.clientHeight,
        1,
        1000,
      ];
      const renderConfig = {
        canvas: this.$refs.canvas,
        alpha: true,
        antialias: true,
      };

      this.camera = new THREE.PerspectiveCamera(...cameraConfig);
      this.renderer = new THREE.WebGLRenderer(renderConfig);
      this.renderer.setSize(
        this.$refs.canvas.clientWidth,
        this.$refs.canvas.clientHeight
      );
      document.body.appendChild(this.renderer.domElement);

      const greyPointLight = new THREE.PointLight("#c4c4c4", 10);
      this.scene.add(greyPointLight);

      const darkBluePointLight = new THREE.PointLight("#222652", 10);
      this.scene.add(darkBluePointLight);

      const hemisphereLight = new THREE.HemisphereLight(
        "#ffffbb",
        "#080820",
        1
      );
      this.scene.add(hemisphereLight);

      const geometry = new THREE.BoxGeometry(1, 1, 1);
      this.material = new THREE.MeshBasicMaterial({ color: "#00ff00" });
      this.cube = new THREE.Mesh(geometry, this.material);
      this.cube.position.x = 3;
      this.cube.position.y = 1;
      this.scene.add(this.cube);

      this.camera.position.z = 5;
    },
    animateCube: function() {
      requestAnimationFrame(this.animateCube);

      this.cube.rotation.x += 0.01;
      this.cube.rotation.y += 0.01;
      this.renderer.render(this.scene, this.camera);
    },
    updateMaterialColor: (color) => {
      const geometry = new THREE.BoxGeometry(1, 1, 1);
      this.material = new THREE.MeshBasicMaterial({ color: color });
      this.cube = new THREE.Mesh(geometry, this.material);
    },
  },
  mounted() {
    this.init3DScene();
    this.animateCube();
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h1 {
  font-size: 24px;
}
#canvas {
  display: block;
  margin: 20px auto;
  height: 100%;
  width: 100%;
}
</style>
