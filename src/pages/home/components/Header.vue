<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input"><span class="iconfont">&#xe632;</span>输入城市/景点/游玩主题
    </div>
    <router-link to="/City">
      <div class="header-right">{{this.city}}<span class="iconfont arrow-icon">&#xe64a;</span></div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>
<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    display :flex
    line-height:$headerHeight
    background:$bgColor
    color: #fff
    .header-left
      width:.64rem
      float:left
      .back-icon
        text-align:center
        font-size:.4rem
    .header-input
      padding-left:.2rem
      flex:1
      height:.64rem
      line-height:.64rem
      margin-top:.12rem
      margin-left:.2rem
      background: #fff
      border-radius: .1rem
      color:#ccc
    .header-right
      float:right
      width: 1.24rem
      text-align:center
      color: white
      .arrow-icon
        font-size:.24rem
        margin-left:0rem
</style>
