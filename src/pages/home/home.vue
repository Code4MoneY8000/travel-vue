<template>
<div>
    <home-header></home-header>
    <header-swiper></header-swiper>
    <header-icon></header-icon>
    <header-recommend></header-recommend>
    <header-weekend></header-weekend>
</div>
</template>

<script>
import HomeHeader from './components/Header'
import HeaderSwiper from './components/Swiper'
import HeaderIcon from './components/icon'
import HeaderRecommend from './components/recommend'
import HeaderWeekend from './components/weekend'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HeaderSwiper,
    HeaderIcon,
    HeaderRecommend,
    HeaderWeekend
  }
}
</script>

<style lang="stylus" scoped>

</style>
