<template>
  <div class="header">
    城市选择
    <router-link to="/" tag="div">
      <div class="iconfont back-icon">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style scoped lang="stylus">
  @import '~styles/varibles.styl'
  .header
    position: relative
    overflow: hidden
    height : ,86rem
    line-height : .86rem
    text-align : center
    color : #fff
    background : $bgColor
    .back-icon
      position: absolute
      left: 0
      top: 0
      text-align: center
      font-size: .3rem
      width: .64rem
</style>
