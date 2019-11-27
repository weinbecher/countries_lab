<template>
  <div id="app">
    <h3>Countries</h3>
    <country-list :countries="countries"></country-list>
    <country-detail :country="selectedCountry"></country-detail>
  </div>
</template>

<script>
import {eventBus} from './main.js'
import CountryList from './components/CountryList.vue';
import CountryDetail from './components/CountryDetail.vue'

export default {
  name: 'app',
  data(){
    return{
      countries:[],
      selectedCountry: null
    }
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(res=>res.json())
    .then(data=>this.countries = data)

    eventBus.$on("country-selected",(country)=>{this.selectedCountry=country})

  },

  components:{
    "country-list": CountryList,
    "country-detail": CountryDetail,
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
