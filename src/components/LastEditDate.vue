<template>
  <dir class="dateDisplay">
    <p>LAST EDITED : {{formatDate(this.date)}}</p>
  </dir>
</template>

<script>
import moment from "moment";

export default {
  name: "LastEditDate",
  props: ["date"],
  methods: {
    formatDate(date) {
      return moment(new Date(date))
        .format("MMMM DD YYYY")
        .toUpperCase();
    }
  }
};
</script>

<style>
.dateDisplay {
  font-size: 10px;
}
</style>