<template>
  <div>
    <home-header></home-header>
    <div class="home">
      {{msg}}
    </div>
  </div>
</template>
<script>
import HomeHeader from './components/Header'
export default {
  name: 'home',
  components: {
    HomeHeader
  },
  data () {
    return {msg: 'this is home'}
  }
}
</script>
