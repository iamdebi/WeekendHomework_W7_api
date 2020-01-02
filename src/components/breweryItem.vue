<template lang="html">
  <div>
    <li v-on:click="onClick">{{brewery.name}}</li>
  </div>
</template>

<script>
import { eventBus } from "../main.js";

export default {
  name: "breweryItem",

  props: ["brewery"],

  methods: {
    onClick() {
      eventBus.$emit("selected-brewery", this.brewery);
    }
  }
};
</script>

<style lang="css" scoped></style>