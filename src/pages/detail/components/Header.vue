<template>
  <div>
    <div class="banner" @click="handleClickBanner">
      <img class="banner-img" :src="bannerImgUrl" />
      <div class="banner-info">
        <div class="banner-intro">
          <span class="iconfont">&#xe600;</span>
          <span class="number">{{bannerList.length}}</span>
        </div>
        <div class="banner-title">{{intro}}</div>
      </div>
    </div>
    <fade-animation>
      <detail-gallary v-show="showGallary" :imgList='bannerList' @close="handleClickGallary"></detail-gallary>
    </fade-animation>
  </div>
</template>

<script>
import DetailGallary from '@/commmon/gallary/Gallary'
import FadeAnimation from '@/commmon/fadeAnimation/FadeAnimation'
export default {
  name: 'DetailHeader',
  data () {
    return {
      showGallary: false
    }
  },
  props: {
    intro: String,
    bannerImgUrl: String,
    bannerList: Array
  },
  components: {
    DetailGallary,
    FadeAnimation
  },
  methods: {
    handleClickBanner () {
      this.showGallary = true
    },
    handleClickGallary () {
      this.showGallary = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-info
      display: flex
      flex-direction: column
      position: absolute
      left: .2rem
      right: .2rem
      bottom: .26rem
      line-height: .6rem
      color: white
      .banner-intro
        width: 1.2rem
        height: .4rem
        padding-left: .2rem
        border-radius: .2rem
        line-height: .4rem
        font-size: .26rem
        text-algin: center
        background: rgb(0, 0, 0, 0.5)
        .number
          margin-left:.1rem
      .banner-title
        flex: 1
        font-size: .36rem
        font-weight: 900
        margin-top: .1rem
</style>
