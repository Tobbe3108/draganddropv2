<template>
  <flickity ref="flickity" :options="flickityOptions" class="carousel">
    <panel-item class="carousel-cell" v-for="item in todos" :key="item.name" :item="item"></panel-item>
  </flickity>
</template>

<script>
import Flickity from "vue-flickity";
import PanelItem from "./PanelItem";

export default {
  name: "panels",
  components: {
    Flickity,
    PanelItem
  },
  data() {
    return {
      flickityOptions: {
        prevNextButtons: false,
        pageDots: false
      }
    };
  },
  props: ["todos"],
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