<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont icon-back">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{this.city}}
        <span class="iconfont arrow-icon">&#xe64a;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'Home',
  computed: {
    ...mapState(['city'])
  }
}
</script>

<style lang="stylus" scoped>
// 1rem = html font-size = 50px
  @import '~styles/varibles.styl'
  .header
    display flex
    line-height $HeaderHeight
    background $bgColor
    color #fff
    .header-left
      width .64rem
      float left
      .icon-back
        font-size .4rem
        text-align center
    .header-input
      flex 1
      background #ffffff
      border-radius .1rem
      margin-top .12rem
      height .64rem
      margin-left .2rem
      color #ccc
      line-height .64rem
      padding-left .2rem
    .header-right
      min-width 1.04rem
      padding 0 0.1rem
      float right
      text-align center
      color #fff
      .arrow-icon
        font-size .24rem
</style>
