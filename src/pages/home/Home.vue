<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <div class="home">
      {{msg}}
    </div>
  </div>
</template>
<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
export default {
  name: 'home',
  components: {
    HomeHeader,
    HomeSwiper
  },
  data () {
    return {msg: 'this is home'}
  }
}
</script>
