<template lang="html">
  <div>
    <h1>American Breweries</h1>
    <div>
      <breweries-list v-bind:breweries="breweries"></breweries-list>
    </div>
    <div>
      <brewery-detail v-bind:brewery="selectedBrewery" v-if="selectedBrewery"></brewery-detail>
    </div>
  </div>
</template>

<script>
import breweries from "./components/breweriesList";
import breweryDetail from "./components/breweryDetail";
import { eventBus } from "./main.js";

export default {
  name: "app",
  data() {
    return {
      breweries: [],
      selectedBrewery: null
    };
  },

  mounted() {
    fetch("https://api.openbrewerydb.org/breweries")
      .then(result => result.json())
      .then(brewery => (this.breweries = brewery));

    eventBus.$on("selected-brewery", brewery => {
      this.selectedBrewery = brewery;
    });
  },

  components: {
    "breweries-list": breweries,
    "brewery-detail": breweryDetail
  }
};
</script>

<style lang="css" scoped></style>
