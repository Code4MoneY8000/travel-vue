<template>
<div>
    <home-header :city='city'></home-header>
    <header-swiper :list='swiperList'></header-swiper>
    <header-icon :list='iconList'></header-icon>
    <header-recommend :list='recommendList'></header-recommend>
    <header-weekend :list='weekendList'></header-weekend>
</div>
</template>

<script>
import HomeHeader from './components/Header'
import HeaderSwiper from './components/Swiper'
import HeaderIcon from './components/icon'
import HeaderRecommend from './components/recommend'
import HeaderWeekend from './components/weekend'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HeaderSwiper,
    HeaderIcon,
    HeaderRecommend,
    HeaderWeekend
  },
  data () {
    return {
      city: '',
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    }
  },
  mounted () {
    this.getHomeInfo()
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret) {
        this.city = res.data.city
        this.swiperList = res.data.swiperList
        this.iconList = res.data.iconList
        this.recommendList = res.data.recommendList
        this.weekendList = res.data.weekendList
      }
    }
  }
}
</script>

<style lang="stylus" scoped>

</style>
