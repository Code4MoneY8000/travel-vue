<template>
  <div>
    <div class="city-rearch">
      <input v-model="keyword" type="text" placeholder="输入城市名或拼音" class="search-input">
    </div>
    <div class="search-content" v-show="keyword">
      <ul>
        <li class="item-content" v-for="item of list" :key='item.id' @click="handleCityChange">{{item.name}}</li>
        <li class="item-content" v-show="hasData">没有找到匹配数据</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'cityrearch',
  props: {
    cities: Object
  },
  computed: {
    hasData () {
      return !this.list.length
    }
  },
  data () {
    return {
      list: [],
      keyword: '',
      timer: null
    }
  },
  methods: {
    handleCityChange (e) {
      this.$store.dispatch('changeCity', e.target.innerText)
      this.$router.push('/')
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
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
  .search-content
    z-index: 1
    background: #eee
    position: absolute
    top: 1.768rem
    left: 0
    right: 0
    bottom: 0
    .item-content
      background: #fff
      line-height: .62rem
      padding-left: .2rem
</style>
