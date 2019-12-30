<template lang="html">
  <div>
    <h1>American Breweries</h1>
    <div>
      <breweries-list v-bind:breweries="breweries"></breweries-list>
    </div>
  </div>
</template>

<script>
import breweries from "./components/breweriesList";

export default {
  name: "app",
  data() {
    return {
      breweries: []
    };
  },

  mounted() {
    fetch("https://api.openbrewerydb.org/breweries")
      .then(result => result.json())
      .then(brewery => (this.breweries = brewery));
  },

  components: {
    "breweries-list": breweries
  }
};
</script>

<style lang="css" scoped></style>
