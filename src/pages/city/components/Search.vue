<template>
  <div>
    <div class="search">
      <input type="text" placeholder="输入城市名或拼音" class="search-input" v-model="keyword">
    </div>
    <div class="search-content" v-show="keyword" ref="content">
      <ul>
        <li class="search-item border-bottom"
            v-for="item of cityList"
            :key="item.id">{{item}}</li>
        <li class="search-item border-bottom"
            v-show="hasNoData">
          没有找到匹配数据
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
import Bscroll from 'better-scroll'
export default {
  name: 'citySearch',
  props: {
    list: Object
  },
  data () {
    return {
      keyword: '',
      cityList: [],
      timer: null
    }
  },
  computed: {
    hasNoData () {
      return !this.cityList.length
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.content)
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.list) {
          this.list[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
              result.push(value.name)
            }
          })
        }
        this.cityList = result
      }, 100)
    }
  }
}
</script>
<style lang="stylus" scoped="">
  @import '~styles/varibles'
  .search
    height: .72rem
    padding: 0 .1rem
    background: $bgColor
    .search-input
      box-sizing: border-box
      width: 100%
      height:.62rem
      padding: 0 .1rem
      line-height: .62rem
      text-align: center
      border-radius: .06rem
      color: #666
  .search-content
    z-index: 1
    overflow: hidden
    position: absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    background: #eee
    .search-item
      line-height: .62rem
      padding-left: .2rem
      background: #fff
      color: #666
</style>
