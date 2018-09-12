<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icons></home-icons>
    <home-recommend></home-recommend>
    <home-weekend></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './components/homeHeader'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/icons'
import HomeRecommend from './components/recommend'
import HomeWeekend from "./components/weekend";
export default {
  name: 'home',
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
