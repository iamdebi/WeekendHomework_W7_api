<template lang="html">
  <ul>
    <brewery-item v-bind:brewery="brewery" v-for="(brewery, index) in breweries"></brewery-item>
  </ul>
</template>

<script>
import breweryItem from "./breweryItem";

export default {
  name: "breweries",
  props: ["breweries"],

  components: {
    "brewery-item": breweryItem
  }
};
</script>

<style lang="css" scoped></style>