<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list :city="cities" :hots="hotCities"></city-list>
    <city-alphabet :city="cities"></city-alphabet>
  </div>
</template>

<script>
import axios from 'axios'
import CityHeader from './components/header'
import CitySearch from './components/search'
import CityList from './components/list'
import CityAlphabet from './components/alphabet'
export default {
  name: 'city',
  components: {
    CityAlphabet,
    CityList,
    CitySearch,
    CityHeader
  },
  data () {
    return {
      cities: {},
      hotCities: []
    }
  },
  methods: {
    getCityInfo () {
      axios.get('/api/city.json').then(
        this.handleCityInfo
      )
    },
    handleCityInfo (res) {
      // console.log(res)
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.cities = data.cities
        this.hotCities = data.hotCities
      }
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>

<style lang="stylus" scoped></style>
