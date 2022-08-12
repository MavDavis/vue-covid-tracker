<template>
  <div class="text-center">
    <h2 class="text-3xl font-bold">{{ text }}</h2>
    <div class="text-2xl mt-4 mb-10">{{ dates }}</div>
  </div>
</template>

<script>
import moment from "moment";
export default {
  name: "Date",
  props: ["date", "text"],
  computed: {
    dates() {
      return moment(this.date).format("MMMM Do YYYY, h:mm:ss a");
    },
  },
};
</script>

<style></style>
