<template>
  <div class="panels_Container">
    <last-edit-date :date="todos[currentIndex].lastEdit" />

    <flickity ref="flickity" :options="flickityOptions" class="carousel">
      <panel-item class="carousel-cell" v-for="item in todos" :key="item.name" :item="item"></panel-item>
    </flickity>
  </div>
</template>

<script>
import Flickity from "vue-flickity";
import PanelItem from "./PanelItem";
import LastEditDate from "./LastEditDate";

export default {
  name: "panels",
  components: {
    Flickity,
    PanelItem,
    LastEditDate
  },
  data() {
    return {
      flickityOptions: {
        prevNextButtons: false,
        pageDots: false
      }
    };
  },
  props: ["todos", "currentIndex"],
  methods: {
    onInit() {
      this.$refs.flickity.on("change", index => {
        this.$emit("changeIndex", index);
      });
    }
  },
  mounted() {
    this.onInit();
  }
};
</script>

<style>
.panel_Container {
  display: flex;
  height: 100vh;
}
.carousel {
  padding-top: 40vh;
  height: 90vh;
}
.carousel-cell {
  width: 75%;
  height: 100%;
  margin-right: 5%;
  background: white;
  border-radius: 10px;
}
</style>