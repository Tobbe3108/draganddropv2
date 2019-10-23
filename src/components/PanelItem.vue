<template>
  <div class="panel_Container">
    <div class="panel_Icon">
      <v-icon :name="item.icon" scale="1.25" :style="{color: item.color}"></v-icon>
    </div>
    <div class="panel_Body">
      <h3 class="panel_Title">{{item.name}}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "panelItem",
  props: ["item"]
};
</script>

<style>
.panel_Container {
  flex: 1;

  /* Padding for whole container */
  padding: 20px;
}
.panel_Icon {
  display: flex;

  /* Size and color of icon border */
  width: 44px;
  height: 44px;
  border: 1px solid #eee;
  border-radius: 100%;

  /* Icon alignment inside border */
  justify-content: center;
  align-items: center;
}
.panel_Body {
  text-align: right;
  transform: translate3d(0, 189px, 0);
  will-change: transform;
}
.panel_Title {
  margin-top: 6px;
  font-size: 32px;
  color: black;
}
</style>