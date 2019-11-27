<template lang="html">
<div v-if= "country">
  <h3>{{country.name}}</h3>
  <ul>
    <li>Capital: {{country.capital}}</li>
    <li>Population: {{country.population}}</li>
  </ul>
</div>
</template>

<script>
export default {
  name: "country-detail",
  props:["country"]
}
</script>

<style lang="css" scoped>
</style>
