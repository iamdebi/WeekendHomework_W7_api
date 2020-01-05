<template lang="html">
  <li v-on:click="onClick">{{brewery.name}}</li>
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

<style lang="css">
body {
  font-family: sans-serif;
}

ul {
  margin: 0;
}

li {
  padding: 6px 0;
  list-style: none;
}

li:hover {
  cursor: pointer;
  opacity: 0.3;
}

ul li p {
  margin: 0;
}
</style>