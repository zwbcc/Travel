<template>
  <div>
    <div class="recommend-title">热销推荐</div>
    <ul class="items">
      <li class="item border-bottom" v-for="item of recommend" :key="item.id">
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
      // recommendList:[
      //   {
      //     id:'001',
      //     imgUrl:'http://img1.qunarzz.com/sight/p0/1709/41/411f234d79457081a3.img.jpg_200x200_ea02ef99.jpg',
      //     title: '广州长隆动物世界',
      //     desc:'尽情享受长隆动物乐园的乐趣'
      //   },
      //   {
      //     id:'002',
      //     imgUrl:'http://img1.qunarzz.com/sight/p0/1707/47/477416df92210439a3.img.jpg_200x200_b9e4ac2c.jpg',
      //     title: '广州长隆欢乐世界',
      //     desc:'尽情享受长隆机动乐园的乐趣'
      //   },
      //   {
      //     id:'003',
      //     imgUrl:'http://img1.qunarzz.com/sight/p0/1707/ab/abb70c851caaa6d8a3.img.jpg_200x200_b902dd9e.jpg',
      //     title: '广州长隆水上世界',
      //     desc:'尽情享受长隆水上乐园的乐趣'
      //   },
      // ]
    }
  },
  props: {
    recommend: Array
  }
}
</script>

<style scoped lang="stylus">
  .recommend-title
    margin-top .2rem
    line-height: .8rem
    background: #eee
    text-indent: .2rem

  .items
    margin-left: 0.24rem
    .item
      display flex
      height: 2rem
      padding: 0.2rem 0
      overflow: hidden
      .item-img
        display block
        width 2rem
        height 2rem
      .item-info
        flex: 1
        padding-left: .1rem
        .item-title
          line-height: .54rem
          font-size: .32rem
        .item-desc
          line-height .4rem
          color: #ccc
        .item-button
          background: #ff9300
          margin-bottom: -.88rem
          padding: 0 .1rem
          border-radius: .06rem

</style>
