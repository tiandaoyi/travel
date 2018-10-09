<template>
  <div>
    <detail-banner></detail-banner>
    <common-gallary></common-gallary>
  </div>
</template>
<script>
import DetailBanner from './components/Banner'
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    CommonGallary
  }
}
</script>
<style lang="stylus" scoped>

</style>
