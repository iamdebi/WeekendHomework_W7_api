<template lang="html">
  <div>
    <ul>
      <li>
        <h3>Brewery Details</h3>
      </li>
      <li>
        <p>Name: {{brewery.name}}</p>
      </li>
      <li>
        <p>Type: {{brewery.brewery_type}}</p>
      </li>
      <li>
        <p>City: {{brewery.city}}</p>
      </li>
      <li>
        <p>State: {{brewery.state}}</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "breweryDetail",
  props: ["brewery"]
};
</script>

<style lang="css" scoped>
ul {
  border: solid;
  padding: 10px;
}

ul li:hover {
  cursor: initial;
  opacity: 1;
}
</style>