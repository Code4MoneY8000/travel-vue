<template>
  <div class="header-wrapper">
    <router-link tag='div' to='/' class="icon-back" v-show='hasShow'>
      <span class="iconfont">&#xe624;</span>
    </router-link>
    <div class="city-header" v-show="!hasShow" :style="opacityStyle">
      <div class="city-header-text">
      城市列表
      </div>
      <router-link to='/'>
        <div class="city-header-back">
            <span class="iconfont">&#xe624;</span>
        </div>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'detail-header',
  data () {
    return {
      hasShow: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      let top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.hasShow = false
      } else {
        this.hasShow = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
.icon-back
  position: absolute
  top: .2rem
  left: .2rem
  width: .8rem
  height: .8rem
  border-radius: .4rem
  background: rgba(0, 0, 0, .8)
  text-align: center
  line-height: .8rem
  .iconfont
    font-size: .4rem
    color: #fff
.city-header
    position: fixed
    top: 0
    left: 0
    right: 0
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
