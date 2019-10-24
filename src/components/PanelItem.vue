<template>
  <div class="panel_Container">
    <div class="panel_Icon">
      <v-icon :name="item.icon" scale="1.25" :style="{color: item.color}"></v-icon>
    </div>
    <div class="panel_Body">
      <h7 class="panel_Items">{{ItemsDisplay(item.items)}}</h7>
      <h3 class="panel_Title">{{item.name}}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "panelItem",
  props: ["item"],
  methods: {
    ItemsDisplay(items) {
      if (items.length == 1) {
        return items.length + " Item";
      } else {
        return items.length + " Items";
      }
    }
  }
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
  display: inline-block;
  padding-bottom: 10px;
  justify-content: left;
  align-items: flex-end;
  position: absolute;
  bottom: 0;
  left: 20;
}
.panel_Title {
  color: black;
}
.panel_Items {
  color: black;
}
</style>