<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div class="iconfont icon-back">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header
  position relative
  background $bgColor
  color #ffffff
  line-height $HeaderHeight
  height $HeaderHeight
  overflow hidden
  text-align center
  font-size 0.32rem
  .icon-back
    color #ffffff
    position absolute
    top 0
    left 0
    width 0.64rem
    text-align center
    font-size 0.4rem
</style>
