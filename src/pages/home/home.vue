<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icons>icons</home-icons>
  </div>
</template>

<script>
import HomeHeader from './components/homeHeader'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/icons'
export default {
  name: 'home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons
  }

}
</script>

<style scoped>

</style>
