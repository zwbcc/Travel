<template>
  <div>
    <div class="search">
      <input type="text" class="search-input" v-model="keyword" placeholder="输入城市或拼音">
    </div>
    <div class="search-content" ref="search" v-show="keyword">
      <ul>
        <li class="search-item border-bottom" v-for="item of list" :key="item.id" @click="handleCityClick(item.name)">
          {{item.name}}
        </li>
        <li class="search-item border-bottom" v-show="hasNoData">没有找到匹配数据</li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CitySearch',
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  methods: {
    handleCityClick (city) {
      this.$store.commit('changeCity', city)
      this.$router.push('/')
    }
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  props: {
    cities: Object
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 ||
            value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  }
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
  .search-content
    z-index: 1
    position: absolute
    top: 1.58rem
    overflow: hidden
    left: 0
    right: 0
    bottom: 0
    background: #eee
    .search-item
      line-height: .62rem
      padding-left : .2rem
      background : #ffffff
      color : #666
</style>
