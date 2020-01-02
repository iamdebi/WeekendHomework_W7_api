<template lang="html">
  <ul>
    <brewery-item v-for="(brewery, index) in breweries" v-bind:brewery="brewery"></brewery-item>
  </ul>
</template>

<script>
import breweryItem from "./breweryItem";

export default {
  name: "filtterd",

  props: ["breweries"],

  components: {
    "brewery-item": breweryItem
  }
};
</script>

<style lang="css" scoped></style>