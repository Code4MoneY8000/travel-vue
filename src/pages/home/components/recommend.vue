<template>
  <div>
      <div class="title">猜你喜欢</div>
      <router-link tag='div' :to="'/detail/'+item.id" class="item" v-for='item of list' :key='item.id'>
        <div class="item-icon">
          <img class="item-img" :src="item.imgUrl" alt="">
        </div>
        <div class="item-info">
          <div class="item-name">
            <p>{{item.title}}</p>
          </div>
          <div class="item-desc">
            <p>{{item.desc}}</p>
          </div>
          <button class="item-moreinfo">查看详情</button>
        </div>
      </router-link>
  </div>
</template>

<script>
export default {
  name: 'HeaderRecommend',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
.title
  line-height: .8rem
  background: #eee
  text-indent: .2rem
  margin-top: .2rem
.item
  margin-top: .2rem
  overflow: hidden
  height: 1.9rem
  display: flex
  .item-img
    width: 1.7rem
    height: 1.7rem
    padding: .1rem
  .item-info
    flex: 1
    padding: .1rem
    .item-name
      line-height: .54rem
      font-size: .32rem
    .item-desc
      line-height: .4rem
      color: #ccc
    .item-moreinfo
      margin-top: .14rem
      background: #ff9300
      padding: .1rem
      border-radius: .06rem
</style>
