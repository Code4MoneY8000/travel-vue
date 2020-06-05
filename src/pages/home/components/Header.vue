<template>
    <div>
        <div class="header">
            <div class="header-left">
                <span class="iconfont">&#xe624;</span>
            </div>
            <div class="header-mid">
                <span class="iconfont">&#xe632;</span>
                输入城市/景点/游玩主题</div>
            <div class="header-right">{{this.city}}
                <span class="iconfont">&#xe62d;</span>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

<style lang="stylus" scoped>
  $bgcolor = #00bcd4
  .header
    display:flex
    line-height: .86rem
    background-color: $bgcolor
    color: #fff
    .header-left
      text-align: center
      width: .64rem
      float: left
    .header-right
      text-align: center
      width: 1.24rem
      float: right
    .header-mid
      flex: 1
      height: .64rem
      padding-left: .2rem
      line-height: .64rem
      background: #fff
      border-radius: .1rem
      margin-top: .12rem
      margin-left: .2rem
      color: #ccc
</style>
