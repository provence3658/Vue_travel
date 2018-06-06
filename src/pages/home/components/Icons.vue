<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img-area">
            <img class="icon-img-context" :src="item.imgUrl" alt="">
          </div>
          <p class="icon-text" v-text="item.desc"></p>
        </div>
      </swiper-slide>
      <!-- <div class="swiper-pagination"  slot="pagination"></div> -->
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        autoplay: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
@import '~styles/mixins.styl'
.icons
  height 0
  padding-bottom 50%
  overflow hidden
  margin-top 0.1rem
  .icon
    float left
    width 25%
    padding-bottom 25%
    position relative
    float left
    overflow hidden
    .icon-img-area
      width 100%
      position absolute
      top 0
      left 0
      right 0
      bottom 0.44rem
      box-sizing border-box
      padding 0.1rem
      .icon-img-context
        height 100%
        display block
        margin 0 auto
    .icon-text
      height 0.44rem
      line-height 0.44rem
      position absolute
      bottom 0
      left 0
      right 0
      text-align center
      color $darkTextColor
      ellipsis()
</style>
