<template>
  <div id="app">
    <search></search>
    <preview :ticker="ticker"></preview>
  </div>
</template>

<script>
import Search from './components/Search.vue'
import Preview from './components/Preview.vue'
import axios from 'axios'

export default {
  name: 'app',
  components: { Search, Preview },
  data() {
    return {
      ticker: []
    }
  },
  created (){
    axios.get(' https://api.coinmarketcap.com/v1/ticker/')
    .then(response => {
      this.ticker = response.data 
    })
    .catch(e => {
      this.errors.push(e);
    })
  }
} 
</script>

<style lang="scss">
#app {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
 
}

