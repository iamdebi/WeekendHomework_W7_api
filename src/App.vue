<template lang="html">
  <h1>American Breweries</h1>
</template>

<script>
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
  }
};
</script>

<style lang="css" scoped></style>
