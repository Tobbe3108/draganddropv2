<template>
  <div id="app">
    <gradient :todos="todos" :currentIndex="currentIndex" />
    <panels :todos="todos" @changeIndex="changeIndex" />
  </div>
</template>

<script>
import Gradient from "./components/Gradient";
import Panels from "./components/Panels";

export default {
  name: "app",
  components: {
    Gradient,
    Panels
  },
  data() {
    return {
      currentIndex: 0,
      todos: [
        {
          icon: "user",
          name: "Personal",
          color: "#ff6262"
        },
        {
          icon: "suitcase",
          name: "Work",
          color: "#5b9df9"
        },
        {
          icon: "home",
          name: "Home",
          color: "#2c7d59"
        }
      ]
    };
  },
  methods: {
    changeIndex(newIndex) {
      this.currentIndex = newIndex;
    }
  }
};
</script>

<style>
#app {
  overflow: hidden;
  color: white;
}
</style>