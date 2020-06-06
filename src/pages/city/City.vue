<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list :hot='hot' :cities='cities' :alpha='alpha'></city-list>
    <city-alphabet :cities='cities' @change='handleChange'></city-alphabet>
  </div>
</template>

<script>
import cityHeader from './components/cityHeader'
import citySearch from './components/citySerach'
import cityList from './components/cityList'
import cityAlphabet from './components/Alphabet'
import axios from 'axios'
export default {
  name: 'City',
  components: {
    cityHeader,
    citySearch,
    cityList,
    cityAlphabet
  },
  data () {
    return {
      hot: [],
      cities: {},
      alpha: ''
    }
  },
  mounted () {
    this.getInfo()
  },
  methods: {
    getInfo () {
      axios.get('/api/city.json')
        .then(this.getInfoSucc)
    },
    getInfoSucc (res) {
      res = res.data
      if (res.ret) {
        this.hot = res.data.hotCities
        this.cities = res.data.cities
      }
    },
    handleChange (e) {
      this.alpha = e
    }
  }
}
</script>

<style lang="stylus" scoped>

</style>
