<template>
  <div class="container" @click="handleGalleryClick">
    <div class="wrapper">
      <swiper :options="swiperOption">
        <swiper-slide v-for="(item, index) in imgs" :key="index">
          <img class="gallery-img" :src="item" alt="">
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CommonGallery',
  props: {
    imgs: {
      type: Array,
      default () {
        return ['http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_r_800x800_d6a63068.jpg', 'http://img1.qunarzz.com/sight/p0/1811/d5/d5153b5e337c0644a3.water.jpg_r_800x800_5785f05e.jpg']
      }
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observer: true,
        observeParents: true
      }
    }
  },
  methods: {
    handleGalleryClick () {
      this.$emit('close')
    }
  }
}
</script>

<style scoped lang="stylus">
.container >>> .swiper-container
  overflow inherit
.container
  display flex
  flex-direction column
  justify-content center
  z-index 99
  position fixed
  left 0
  right 0
  top 0
  bottom 0
  background #000
  .wrapper
    width 100%
    height 0
    padding-bottom 100%
    .gallery-img
      width 100%
    .swiper-pagination
      bottom -1rem
      color #fff
</style>
