<template>
  <div>
      <div class="title">周末去哪儿</div>
      <div class="item" v-for='item of list' :key='item.id'>
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
        </div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'Headerweekend',
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
  .item-icon
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 37.09%
    .item-img
      width: 100%
  .item-info
    padding: .1rem
    text-indent: .2rem
    .item-name
      line-height: .54rem
      font-size: .32rem
    .item-desc
      line-height: .4rem
      color: #ccc
</style>
