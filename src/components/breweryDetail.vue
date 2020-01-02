<template lang="html">
  <div>
    <ul>
      <p>Name: {{brewery.name}}</p>
      <p>Type: {{brewery.brewery_type}}</p>
      <p>City: {{brewery.city}}</p>
      <p>State: {{brewery.state}}</p>
    </ul>
  </div>
</template>

<script>
export default {
  name: "breweryDetail",
  props: ["brewery"]
};
</script>

<style lang="css" scoped></style>