<template>
  <div id="app">
    <gradient :todos="todos" :currentIndex="currentIndex" />
    <panel :todos="todos" @changeIndex="changeIndex" />
  </div>
</template>

<script>
import Gradient from "./components/Gradient";
import Panel from "./components/Panel";

export default {
  name: "app",
  components: {
    Gradient,
    Panel
  },
  data() {
    return {
      currentIndex: 0,
      todos: [
        {
          name: "Personal",
          color: "#ff6262"
        },
        {
          name: "Work",
          color: "#5b9df9"
        },
        {
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