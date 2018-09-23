<template>
  <ul class="list">
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
  </ul>
</template>
<script>
export default {
  name: 'CityAlphabet'
}
</script>
<style lang="stylus" scoped="">
  @import '~styles/varibles'
  .list
    position: absolute
    right: 0
    top: 1.58rem
    bottom: 0
    display: flex
    flex-direction: column
    justify-content: center
    .item
      text-align: center
      line-height: .4rem
      color: $bgColor
</style>
