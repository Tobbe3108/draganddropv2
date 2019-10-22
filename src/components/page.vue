<template>
  <div class="slider">
    <div>Slide #1</div>
    <div>Slide #2</div>
    <div>Slide #3</div>
    <div>Slide #4</div>
    <div>Slide #5</div>
  </div>
</template>

<script>
export default {
  name: "page"
};
</script>

<style>
.slider {
  width: 100%;
  text-align: center;
  overflow: hidden;
}
.slider {
  display: flex;

  overflow-x: auto;
  scroll-snap-type: x mandatory;

  scroll-behavior: smooth;
  -webkit-overflow-scrolling: touch;
}
.slider > div {
  scroll-snap-align: start;
  flex-shrink: 0;
  width: 100%;
  height: 300px;
  background: #eee;
}
</style>

