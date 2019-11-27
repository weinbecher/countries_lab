<template lang="html">
<div>
  <ul>
    <country-list-item v-for ="(country,index) in countries" :country="country" :key="index"></country-list-item>

  </ul>

</div>
</template>

<script>
import CountryListItem from './CountryListItem.vue'

export default {
  name: "country-list",
  props: ["countries"],
  components:{
    "country-list-item":CountryListItem
  }

}
</script>

<style lang="css" scoped>
</style>
