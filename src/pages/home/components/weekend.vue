<template>
  <div>
    <div class="weekend-title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of weekendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img-cont" :src="item.imgUrl" alt="">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data() {
    return {
      weekendList: [
        {
          id:'001',
          imgUrl:'http://img1.qunarzz.com/sight/source/1505/92/580e9ea4f37a1b.jpg_r_640x214_72112761.jpg',
          title:'广州必游TOP10',
          desc:'感受现代与传统相融合的广州'
        },
        {
          id:'002',
          imgUrl:'http://img1.qunarzz.com/sight/source/1505/53/02091f1ee43d0a.jpg_r_640x214_2e3256b1.jpg',
          title:'北京清凉避暑胜地',
          desc:'到大自然中享受“天然空调”的清凉'
        },
        {
          id:'003',
          imgUrl:'http://img1.qunarzz.com/sight/source/1606/85/c6b6bad1b977e.jpg_r_640x214_5c638941.jpg',
          title:'漂流勇进，烧烤露营',
          desc:'轻松水上漂，任我乐逍遥'
        },
        {
          id:'004',
          imgUrl:'http://img1.qunarzz.com/sight/source/1505/ce/bc89bc2f0e33ea.jpg_r_640x214_3e408453.jpg',
          title:'学生最爱的博物馆',
          desc:'周末干嘛？北京很多博物馆已经免费开放啦'
        },
      ]
    }
  }
}
</script>

<style scoped lang="stylus">
.weekend-title
  height: .8rem;
  padding-left: .26rem;
  line-height: .8rem;
  color: #212121;
.item-img-wrapper
  overflow: hidden;
  height : 0;
  padding-bottom : 37.4375%;
  .item-img-cont
    width: 100%
.item-info
  flex : 1
  padding-left: .1rem
  .item-title
    padding-right: 1.4rem;
    color: #212121;
    font-size: .28rem;
    line-height: .48rem
  .item-desc
    padding-right: 1.4rem;
    color: #616161;
    font-size: .24rem;
    line-height: .42rem
  .item-button
    background : #ff9300
    margin-bottom : -.88rem
    padding : 0 .1rem
    border-radius : .06rem
</style>
