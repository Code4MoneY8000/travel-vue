<template>
<div class="icons">
  <swiper :options="swiperOptions">
    <swiper-slide v-for="(page, index) of pages" :key="index">
      <div class="icon" v-for="item of page" :key='item.id'>
        <div class="icon-img">
          <img class="icon-img-content" :src="item.imgUrl" alt="">
        </div>
        <p class="icon-text">{{item.desc}}</p>
      </div>
    </swiper-slide>
  </swiper>
</div>

</template>

<script>
export default {
  name: 'Header-icon',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOptions: {
        autoplay: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  .icons
    margin-top: .1rem
    .icon
      position: relative
      overflow: hidden
      float: left
      width: 25%
      height: 0
      padding-bottom: 25%
      .icon-img
        position: absolute
        top: 0
        left: 0
        right: 0
        bottom: .44rem
        .icon-img-content
          height: 100%
          display: block
          margin:0 auto
      .icon-text
        position:absolute
        bottom: 0
        left: 0
        right: 0
        line-height: .44rem
        height: .44rem
        text-align: center
</style>
