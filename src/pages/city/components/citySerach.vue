<template>
  <div class="city-rearch">
    <input type="text" placeholder="输入城市名或拼音" class="search-input">
  </div>
</template>

<script>
export default {
  name: 'cityrearch'
}
</script>

<style lang="stylus" scoped>
  .city-rearch
    background: #00bcd4
    height: 0.72rem
    line-height: .72rem
    padding: .1rem
    .search-input
      box-sizing: border-box
      padding: 0 .1rem
      width: 100%
      line-height: .62rem
      height: .62rem
      text-align: center
      border-radius: .06rem
      color: #666
</style>
