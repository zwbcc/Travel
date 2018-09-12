<template>
  <div CLASS="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
    </div>
    <div class="header-right">
      广州
      <span class="iconfont arrow-icon" >&#xe64a;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'homeHeader',
}
</script>

<style scoped lang="stylus">
  @import '~styles/varibles.styl';
  .header
    display :flex
    height: .86rem
    background-color: $bgColor;
    color : #ffffff
    line-height :.86rem
    .header-left
      width: .64rem
      float: left
      .back-icon
        text-align: center
        font-size : .4rem
    .header-input
      flex: 1
      height: .64rem
      line-height .64rem
      margin-left: .2rem
      padding-left: .2rem
      background: #ffffff
      margin-top .12rem
      border-radius: .1rem
      color : #ccc
    .header-right
      width :1.24rem
      text-align: center
      float: right
      .arrow-icon
        font-size .24rem
        margin-left -.04rem
</style>
