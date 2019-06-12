<template>
  <div class="wrapper">
  <swiper :options="swiperOption">
    <swiper-slide v-for="item of swiperList" :key="item.id">
      <img class="swiper-img" :src="item.imgUrl" alt="">
    </swiper-slide>
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [
        {id: '0001', imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20195/667757f979fa38b12c4986f9930b6695.jpg_750x200_6cca7add.jpg'},
        {id: '0002', imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/87a224d0349d94a11e97f31aa1aba4f5.jpg_750x200_1f78af87.jpg'},
        {id: '0003', imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/e1e587f554e5a8372be44a4c6b73a5cf.jpg_750x200_5732f03f.jpg'},
        {id: '0004', imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20196/3a3066c073a492c1a881607181ac84ab.jpg_750x200_ca7fff4c.jpg'}
      ]
    }
  }
}
</script>

<style scoped lang="stylus">
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff;
.wrapper
  overflow: hidden;
  width: 100%;
  height: 0;
  padding-bottom 26.66%;
  background: #ccc;
.swiper-img
  width: 100%
</style>
