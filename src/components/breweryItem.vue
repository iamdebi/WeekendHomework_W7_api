<template lang="html">
  <div>
    <li>{{brewery.name}}</li>
  </div>
</template>

<script>
export default {
  name: "breweryItem",
  props: ["brewery"]
};
</script>

<style lang="css" scoped></style>