<template>
  <div>
    <div class="detail-banner" @click='handleShow'>
        <img class="banner-img" :src="bannerImg" alt="">
        <div class="banner-info">
        <div class="banner-text">
            {{sightName}}
        </div>
        <div class="banner-number">
            <span class="iconfont">&#xe64a;</span>
            {{imgs.length}}
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
  props: {
    sightName: String,
    bannerImg: String,
    imgs: Array
  },
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
