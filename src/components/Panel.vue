<template>
  <flickity ref="flickity" :options="flickityOptions" class="carousel">
    <div class="carousel-cell" v-for="item in todos" :key="item.name"></div>
  </flickity>
</template>

<script>
import Flickity from "vue-flickity";

export default {
  name: "panel",
  components: {
    Flickity
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
  padding-top: 30vh;
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