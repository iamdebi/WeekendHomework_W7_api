<template lang="html">
  <div>
    <h1>American Breweries</h1>
    <input type="text" name="search" v-model="searchedWord" placeholder="search a Brewery ..." />
    <div>
      <!-- <breweries-list v-bind:breweries="breweries"></breweries-list> -->
      <filtered-list v-bind:breweries="filteredList"></filtered-list>
    </div>
    <div>
      <brewery-detail v-bind:brewery="selectedBrewery" v-if="selectedBrewery"></brewery-detail>
    </div>
    <div id="mapid"></div>
  </div>
</template>

<script>
import breweries from "./components/breweriesList";
import breweryDetail from "./components/breweryDetail";
import { eventBus } from "./main.js";
import filtered from "./components/breweryFiltered";

export default {
  name: "app",
  data() {
    return {
      breweries: [],
      selectedBrewery: null,
      searchedWord: ""
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
    "brewery-detail": breweryDetail,
    "filtered-list": filtered
  },

  computed: {
    filteredList() {
      return this.breweries.filter(brewery => {
        return brewery.name
          .toLowerCase()
          .includes(this.searchedWord.toLowerCase());
      });
    }
  }
};
</script>

<style lang="css" scoped>
ul {
  list-style: none;
  padding: 10px;
}

#mapid {
  height: 180px;
}
</style>

