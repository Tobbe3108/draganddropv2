<template>
  <div id="app">
    <gradient :todos="todos" :currentIndex="currentIndex" />
    <panels :todos="todos" :currentIndex="currentIndex" @changeIndex="changeIndex" />
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
          items: [],
          color: "#ff6262",
          lastEdit: "2019-10-24"
        },
        {
          icon: "suitcase",
          name: "Work",
          items: [name],
          color: "#5b9df9",
          lastEdit: "2019-10-20"
        },
        {
          icon: "home",
          name: "Home",
          items: [name, name, name],
          color: "#2c7d59",
          lastEdit: "2019-05-12"
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