<template>
  <div>
    <router-link class="header-abs" tag="div" to="/" v-show="absShow">
      <div class="iconfont abs-back-icon">&#xe624;</div>
    </router-link>
    <div class="header-title" v-show="!absShow" :style="opacityStyle">
      景点详情
      <router-link to="/" >
        <div class="iconfont title-back-icon">&#xe624;</div>
      </router-link>
    </div>
    <div class="content"></div>
  </div>
</template>
<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      absShow: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    changeScroll () {
      const scrollTop = document.documentElement.scrollTop
      if (scrollTop > 60) {
        let opacity = scrollTop / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.absShow = false
      } else {
        this.absShow = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.changeScroll)
  }
}
</script>
<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header-abs
    position: absolute
    top: .2rem
    left: .2rem
    height: .8rem
    width: .8rem
    line-height: .8rem
    border-radius: .4rem
    color: #ffffff
    background-color: rgb(0,0,0,.6)
    .abs-back-icon
      text-align: center
      font-size: .4rem
  .header-title
    position: fixed
    top: 0
    left: 0
    right: 0
    height: $headerHeight
    line-height: $headerHeight
    text-align: center
    color: #fff
    background: $bgColor
    font-size: .32rem
    .title-back-icon
      position: absolute
      left: 0
      top: 0
      width: .64rem
      text-align: center
      font-size: .4rem
      color: #fff
  .content
    height: 50rem
</style>
