<template lang="html">
  <ul>
    <li v-for="(brewery, index) in breweries">{{brewery.name}}</li>
  </ul>
</template>

<script>
export default {
  name: "breweries",
  props: ["breweries"]
};
</script>

<style lang="css" scoped></style>