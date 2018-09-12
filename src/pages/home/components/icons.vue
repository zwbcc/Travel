<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page , index) of pages"  :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl" alt="">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      swiperOption: {
        loop: false,
        autoplay: false
      }
      // iconList: [
      //   {
      //     id: '001',
      //     imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
      //     desc: '景点门票'
      //   },
      //   {
      //     id: '002',
      //     imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
      //     desc: '广州必游'
      //   },
      //   {
      //     id: '003',
      //     imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
      //     desc: '动植物园'
      //   },
      //   {
      //     id: '004',
      //     imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png',
      //     desc: '游乐场'
      //   },
      //   {
      //     id: '005',
      //     imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/89/55083b0f1951f302.png',
      //     desc: '两江夜游'
      //   },
      //   {
      //     id: '006',
      //     imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/6a/45f595250c73d102.png',
      //     desc: '夏日玩水'
      //   },
      //   {
      //     id: '007',
      //     imgUrl: 'http://img1.qunarzz.com/piao/fusion/1808/8d/747c9a29b8dba402.png',
      //     desc: '网红套餐'
      //   },
      //   {
      //     id: '008',
      //     imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
      //     desc: '一日游'
      //   },
      //   {
      //     id: '009',
      //     imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/b1/528a9e80403b8c02.png',
      //     desc: '热门景点'
      //   }]
    }
  },
  props : {
    iconList: Array
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
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

<style scoped lang="stylus">
  @import '~styles/varibles.styl'
  @import '~styles/mixsin.styl'
  .icons >>> .swiper-container
    height: 0
    padding-bottom: 50%
  .icons
    margin-top : .1rem
    .icon
      overflow hidden
      position: relative
      float: left
      width: 25%
      padding-bottom: 25%
      height: 0
      .icon-img
        position: absolute
        top: 0
        left: 0
        right: 0
        bottom: .44rem
        box-sizing: border-box
        padding: .1rem
        .icon-img-content
          display: block
          margin: 0 auto
          height: 100%
      .icon-desc
        position: absolute
        height: .44rem
        text-align: center
        line-height: .44rem
        left: 0
        bottom: 0
        right: 0
        color: $darkTextColor
        ellipse()

</style>
