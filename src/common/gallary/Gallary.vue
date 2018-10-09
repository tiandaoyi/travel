<template>
  <div class="container" @click="handleGallaryClick">
    <div class="wrapper">
      <swiper :options="swiperOption" >
        <swiper-slide
          v-for="(item, index) in imgs"
          :key="index"
        >
          <img class="gallary-img" :src="item" alt="">
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>
<script>
export default {
  name: 'CommonGallary',
  props: {
    imgs: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      list: [{
        id: 1,
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1805/7d/7dca9c37a87479eba3.img.jpg_600x330_77f48209.jpg'
      }, {
        id: 2,
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1609/80/8092254b7f5f016ea3.water.jpg_r_800x800_0260d706.jpg'
      }],
      swiperOption: {
        pagination: '.swiper-pagination',
        observeParents: true,
        observer: true,
        paginationType: 'fraction'
      }
    }
  },
  methods: {
    handleGallaryClick () {
      this.$emit('close')
    }
  }
}
</script>
<style lang="stylus" scoped>
  .container >>> .swiper-container
    overflow: inherit
  .container
    display: flex
    flex-direction: column
    justify-content: center
    position: fixed
    z-index: 100
    top: 0
    left: 0
    right: 0
    bottom: 0
    background: #000000
    .wrapper
      width: 100%
      height: 0
      padding-bottom: 55%
      .gallary-img
        width: 100%
      .swiper-pagination
        color: #fff
        bottom: -1rem
</style>
