<template>
  <div class="home">
    <Header/>
    This is home <br>
    this is some info <br>
    <div class="bitcoin-info">
      <div> Updated:  {{info.time.updated}} </div>
      <div> Disclaimer: {{info.disclaimer}} </div>
      <div> {{info.chartName}} </div>
      <div v-for="currency in info.bpi" class="currency" :key="currency.code" >
        {{ currency.description }}: {{ currency.rate_float }} <span v-html="currency.symbol"></span>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '../components/Header.vue'
import axios from 'axios'

export default {
  name: 'home',
  components: {
    Header
  },
  data () {
    return {
      info: null
    }
  },
  mounted () {
    axios
      .get('https://api.coindesk.com/v1/bpi/currentprice.json')
      .then(response => (this.info = response.data))
  }
}
</script>
