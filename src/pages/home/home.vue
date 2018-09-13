<template>
  <div>
    <home-header :city="city"></home-header>
    <home-swiper :swiperList="swiperList"></home-swiper>
    <home-icons :iconList="iconList"></home-icons>
    <home-recommend :recommend="recommend"></home-recommend>
    <home-weekend :weekendList="weekendList"></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './components/homeHeader'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/icons'
import HomeRecommend from './components/recommend'
import HomeWeekend from './components/weekend'

export default {
  name: 'home',
  data () {
    return {
      city: '',
      swiperList: [],
      iconList: [],
      recommend: [],
      weekendList: []
    }
  },
  methods: {
    getHomeInfo () {
      this.axios.get('/api/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.city = data.city
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.recommend = data.recommendList
        this.weekendList = data.weekendList
      }
    }
  },
  mounted () {
    this.getHomeInfo()
  },
  components: {
    HomeWeekend,
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend
  }

}
</script>

<style scoped>

</style>
