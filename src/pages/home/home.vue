<template>
<div>
    <home-header></home-header>
    <header-swiper></header-swiper>
    <header-icon></header-icon>
</div>
</template>

<script>
import HomeHeader from './components/Header'
import HeaderSwiper from './components/Swiper'
import HeaderIcon from './components/icon'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HeaderSwiper,
    HeaderIcon
  }
}
</script>

<style lang="stylus" scoped>

</style>
