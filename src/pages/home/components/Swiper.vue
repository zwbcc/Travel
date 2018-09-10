<template>
  <div class="swiper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key = item.id>
        <img class="swiper-img" :src="item.imgUrl"  alt="">
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
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
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1806/1c/4847ea66072c7b02.jpg_750x200_c32457fb.jpg'
        },
        {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1809/b4/7101381b7b2c0702.jpg_750x200_b8da41bf.jpg'
        },
        {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1805/e8/14b75b1c81fbe702.jpg_750x200_e6d4f1f1.jpg'
        }
      ]
    }
  }
}
</script>

<style scoped lang="stylus">
 .swiper >>> .swiper-pagination-bullet-active
   background : #fff
 .swiper
   overflow:hidden
   width:100%
   height:0
   padding-bottom:26.60%
   .swiper-img
     width: 100%
</style>
