<template>
  <div class="city-header">
    <div class="city-header-text">
      城市列表
    </div>
    <router-link to='/'>
      <div class="city-header-back">
        <span class="iconfont">&#xe624;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'cityheader'
}
</script>

<style lang="stylus" scoped>
  .city-header
    position: relative
    height: .86rem
    line-height: .86rem
    text-align: center
    font-size: .32rem
    background: #00bcd4
    color: #fff
    .city-header-back
      position: absolute
      top: 0
      left: 0
      width: .64rem
      color: #fff
</style>
