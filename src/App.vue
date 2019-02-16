<template>
  <div id="app">
    <Dashboard v-bind:currentPriceValue='currentPriceValueData'/>
  </div>
</template>

<script>
import Dashboard from './components/Dashboard.vue'
import axios from 'axios';
axios.defaults.headers.common['authorization'] = process.env.VUE_APP_CRYPTOCOMPARE_KEY

export default {
  name: 'app',
  components: {
    Dashboard
  },
  data: function() {
    return {
     currentPriceValueData: {} 
    }
  },
  ////  Vue lifecycle hooks
  mounted: function() {
    axios.get('https://min-api.cryptocompare.com/data/price?fsym=BTC&tsyms=USD,JPY,EUR')
    .then((response) => {
      // console.log(response.data)
      this.currentPriceValueData = response.data
    })
    .catch((error) => console.log(`Danger Front-End error ${ error }`));
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
