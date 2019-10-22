<template>
  <div class="gradient">
    <gradient-color
      v-for="(todo, index) in todos"
      :key="todo.name"
      :color="todo.color"
      :active="index <= currentIndex"
    />
  </div>
</template>

<script>
import GradientColor from "./GradientColor";

export default {
  name: "gradient",
  components: {
    GradientColor
  },
  props: ["todos", "currentIndex"]
};
</script>

<style>
.gradient {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  z-index: -1;
}
</style>