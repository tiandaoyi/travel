<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list :list="cities" :hotCities="hotCities" :letter="letter"></city-list>
    <city-alphabet :list="cities" @change="handleLetter"></city-alphabet>
  </div>
</template>
<script>
import cityHeader from './components/Header'
import citySearch from './components/Search'
import cityList from './components/List'
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
      hotCities: [],
      cities: {},
      letter: ''
    }
  },
  methods: {
    getCityInfo: function () {
      axios.get('/api/city.json')
        .then(this.getCityInfoSucc)
    },
    getCityInfoSucc: function (res) {
      res = res.data
      if (res && res.data) {
        const data = res.data
        this.hotCities = data.hotCities
        this.cities = data.cities
      }
    },
    handleLetter: function (letter) {
      this.letter = letter
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>
<style lang="stylus" scoped="">

</style>
