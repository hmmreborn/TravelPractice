<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item in recommendList" :key="item.id">
        <img class="item-img" :src="item.imgUrl" alt="">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [
        { id: '0001',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
          title: '上海迪士尼乐园',
          desc: '全球最大的迪士尼城堡'
        },
        { id: '0002',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1904/d5/d579b03a110d75a8a3.img.jpg_200x200_740bd4c0.jpg',
          title: '上海野生动物园',
          desc: '会跳芭蕾的小海狮们~'
        },
        { id: '0003',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1904/6e/6edffb73a665bc70a3.img.jpg_200x200_0e892907.jpg',
          title: '上海海昌海洋公园',
          desc: '浦东新区~'
        }
      ]
    }
  }
}
</script>

<style scoped lang="stylus">
  @import "~styles/mixins.styl"
.title
  margin-top .2rem
  line-height .8rem
  background #eee
  text-indent .2rem
.item
  overflow hidden
  display flex
  height 1.9rem
  padding .1rem
  .item-img
    width 1.7rem
    height 1.7rem
    padding .1rem
  .item-info
    flex:1
    padding .2rem
    min-width 0
    .item-title
      line-height .54rem
      font-size .32rem
      ellipse()
    .item-desc
      line-height .4rem
      color #ccc
      ellipse()
    .item-button
      line-height .44rem
      margin-top .16rem
      color: #fff
      background #ff9300
      padding:0 .2rem
      border-radius .06rem
</style>
