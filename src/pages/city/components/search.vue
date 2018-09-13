<template>
<div class="search">
  <input type="text" class="search-input" placeholder="输入城市或拼音">
</div>
</template>

<script>
export default {
  name: 'CitySearch'
}
</script>

<style scoped lang="stylus">
@import '~styles/varibles.styl'
  .search
    height .72rem
    padding: 0 .1rem
    background: $bgColor
    .search-input
      box-sizing: border-box
      height: .62rem
      width: 100%
      text-align: center
      border-radius : .06rem
      line-height: .62rem
      color: #666
      padding: 0 .1rem
</style>
