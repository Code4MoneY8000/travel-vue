<template>
  <div class="list" ref='wrapper'>
    <div>
      <div class="area">
        <div class="header border-topbottom">当前城市</div>
        <div class="buttonlist">
            <div class="button-wrapper">
                <div class="button">
                    北京
                </div>
            </div>
        </div>
      </div>
      <div class="area">
        <div class="header border-topbottom">热门城市</div>
        <div class="buttonlist">
            <div class="button-wrapper" v-for="item of hot" :key="item.id">
                <div class="button">
                    {{item.name}}
                </div>
            </div>
        </div>
      </div>
      <div class='area' v-for="(item,key) of cities" :key="key">
        <div class="header border-topbottom">{{key}}</div>
          <div class="item-list" v-for="inneritem of item" :key="inneritem.id">
              <div class="item">{{inneritem.name}}</div>
          </div>
        </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'citylist',
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  },
  props: {
    hot: Array,
    cities: Object
  }
}
</script>

<style lang="stylus" scoped>
  .border-topbottom
    &:before
      border-color: #cccccc
    &:after
      border-color: #cccccc
  .list
    overflow: hidden
    position: absolute
    top: 1.78rem
    left: 0
    right: 0
    bottom: 0
    .header
      line-height: .54rem
      background: #eee
      padding-left: .2rem
      color: #666
      font-size: .26rem
    .buttonlist
      padding: .1rem .6rem .1rem .1rem
      overflow: hidden
      .button-wrapper
        float: left
        width: 33%
        .button
          padding: .1rem 0
          text-align: center
          margin: .1rem
          border: .02rem  solid  #ccc
          border-radius: .06rem
    .item-list
      .item
        padding-left: .2rem
        line-height: .76rem
</style>
