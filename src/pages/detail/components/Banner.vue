<template>
  <div>
     <div class="banner" @click="handleBannerClick">
       <img class="banner-img" :src="bannerImg" alt="">
       <div class="banner-info">
         <div class="banner-title">{{this.sightName}}</div>
         <div class="banner-num">
           <span class="iconfont banner-icon">&#xe674;</span>&nbsp;{{this.galleryImgs.length}}
         </div>
       </div>
     </div>
    <fade-animation>
    <common-gallery
      :imgs="galleryImgs"
      v-show="showGallery"
      @close="handleGalleryClose"></common-gallery>
    </fade-animation>
  </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
import FadeAnimation from 'common/fade/Fade'
export default {
  name: 'DetailBanner',
  props: {
    sightName: String,
    bannerImg: String,
    galleryImgs: Array
  },
  components: {
    CommonGallery,
    FadeAnimation
  },
  data () {
    return {
      showGallery: false
    }
  },
  methods: {
    handleBannerClick: function () {
      this.showGallery = true
    },
    handleGalleryClose: function () {
      this.showGallery = false
    }
  }
}
</script>

<style scoped lang="stylus">
.banner
  overflow hidden
  position relative
  height 0
  padding-bottom 55%
  .banner-img
    width 100%
  .banner-info
    display flex
    position absolute
    left 0
    right 0
    bottom 0
    line-height .6rem
    color: #fff
    background: linear-gradient(to bottom,  rgba(0,0,0,0) 0%,rgba(0,0,0,0.08) 100%);
    .banner-title
        flex 1
        font-size .32rem
        padding .2rem
    .banner-num
        margin-top .32rem
        padding:0 .2rem
        line-height .36rem
        height .36rem
        border-radius .2rem
        background rgba(0,0,0,.5)
        font-size .24rem
        .banner-icon
          font-size .24rem
</style>
