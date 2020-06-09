<template>
  <div>
    <div class="detail-banner" @click='handleShow'>
        <img class="banner-img" src="//img1.qunarzz.com/sight/p0/201403/07/579ea27e6d965f0431939720edb7dc0a.jpg_600x330_9a3c4ab0.jpg" alt="">
        <div class="banner-info">
        <div class="banner-text">
            江南第一漂(AAA景区)
        </div>
        <div class="banner-number">
            <span class="iconfont">&#xe64a;</span>
            10
        </div>
        </div>
    </div>
    <gallary class="banner-gallary" :imgs='imgs' v-show="showGallary" @close='handleShow'></gallary>
  </div>
</template>

<script>
import gallary from 'common/gallary/Gallary'
export default {
  name: 'detail-banner',
  components: {
    gallary
  },
  methods: {
    handleShow () {
      this.showGallary = !this.showGallary
    }
  },
  data () {
    return {
      imgs: ['http://img1.qunarzz.com/sight/p0/201403/07/579ea27e6d965f0431939720edb7dc0a.jpg_r_800x800_6249d8a7.jpg', 'http://img1.qunarzz.com/sight/p0/201403/07/e068e7c4a5fd74bc74a60af5952da0a3.jpg_r_800x800_0e9016b7.jpg',
        'http://img1.qunarzz.com/sight/p0/201403/07/adcaac18eb93235e6925c7829ee5dd14.jpg_r_800x800_40eb92ea.jpg'],
      showGallary: false
    }
  }
}
</script>

<style lang="stylus" scoped>
.detail-banner
  position: relative
  overflow: hidden
  height: 0
  padding-bottom: 55%
  .banner-img
    width: 100%
  .banner-info
    display: flex
    position: absolute
    bottom: 0
    left: 0
    right: 0
    line-height: .6rem
    color: #fff
    background-image: linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,.8))
    .banner-text
      flex: 1
      font-size: .32rem
      padding: 0 .2rem
    .banner-number
      padding: 0 .4rem

</style>
