<template>
  <div
    class="gradient_color"
    :class="{ gradient_color__active: active }"
    :style="{ backgroundImage: gradientColor }"
  />
</template>

<script>
export default {
  name: "gradient-color",
  props: {
    color: {
      type: String
    },
    active: {
      type: Boolean
    }
  },
  computed: {
    gradientColor() {
      const colorTop = `to(${this.color})`;
      const colorBottom = `color-stop(30%, ${this.ColorLuminance(
        this.color,
        0.5
      )})`;
      return `-webkit-gradient(linear, left bottom, left top, ${colorBottom}, ${colorTop})`;
    }
  },
  methods: {
    ColorLuminance(hex, lum) {
      // validate hex string
      hex = String(hex).replace(/[^0-9a-f]/gi, "");
      if (hex.length < 6) {
        hex = hex[0] + hex[0] + hex[1] + hex[1] + hex[2] + hex[2];
      }
      lum = lum || 0;

      // convert to decimal and change luminosity
      var rgb = "#",
        c,
        i;
      for (i = 0; i < 3; i++) {
        c = parseInt(hex.substr(i * 2, 2), 16);
        c = Math.round(Math.min(Math.max(0, c + c * lum), 255)).toString(16);
        rgb += ("00" + c).substr(c.length);
      }

      return rgb;
    }
  }
};
</script>

<style>
.gradient_color {
  position: absolute;
  width: 100%;
  height: 100%;
  opacity: 0;
  transition: opacity 0.5s ease;
}
.gradient_color__active {
  opacity: 1;
}
</style>