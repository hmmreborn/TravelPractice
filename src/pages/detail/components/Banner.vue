<template>
  <div>
     <div class="banner" @click="handleBannerClick">
       <img class="banner-img" src="http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_600x330_8572a930.jpg" alt="">
       <div class="banner-info">
         <div class="banner-title">上海迪士尼乐园</div>
         <div class="banner-num">
           <span class="iconfont banner-icon">&#xe674;</span>&nbsp;69
         </div>
       </div>
     </div>
    <common-gallery :imgs="imgs" v-show="showGallery" @close="handleGalleryClose"></common-gallery>
  </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallery
  },
  data () {
    return {
      showGallery: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_r_800x800_d6a63068.jpg', 'http://img1.qunarzz.com/sight/p0/1811/d5/d5153b5e337c0644a3.water.jpg_r_800x800_5785f05e.jpg']
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
