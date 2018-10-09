<template>
  <div>
    <div class="banner" @click="hanldBannerClick">
      <img src="http://img1.qunarzz.com/sight/p0/1805/7d/7dca9c37a87479eba3.img.jpg_600x330_77f48209.jpg" alt="" class="banner-img">
      <div class="banner-info">
        <div class="banner-title">大连圣亚海洋世界(AAAA景区)</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe716;</span>
          39
        </div>
      </div>
    </div>
    <common-gallary
      :imgs="imgs"
      v-show="showGallary"
      @close="handleGallaryClose"
    >
    </common-gallary>
  </div>
</template>
<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  data () {
    return {
      showGallary: false,
      imgs: [
        'http://img1.qunarzz.com/sight/p0/1805/7d/7dca9c37a87479eba3.img.jpg_600x330_77f48209.jpg',
        'http://img1.qunarzz.com/sight/p0/1609/80/8092254b7f5f016ea3.water.jpg_r_800x800_0260d706.jpg'
      ]
    }
  },
  components: {
    CommonGallary
  },
  methods: {
    hanldBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  }
}
</script>
<style lang="stylus" scoped>
  .banner
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 55%
    position: relative
    .banner-img
      width:100%
    .banner-info
      display: flex
      position: absolute
      bottom: 0
      right: 0
      left: 0
      color: #fff
      line-height: .6rem
      background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
      .banner-title
        flex: 1
        font-size: .32rem
        padding: 0 .2rem
      .banner-number
        height: .32rem
        line-height: .32rem
        margin-top: .14rem
        padding: 0 .4rem
        border-radius: .2rem
        background: rgba(0, 0, 0, .8)
        font-size: .24rem
        .banner-icon
          font-size: .24rem
</style>
