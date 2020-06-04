<template>
<div class="icons">
  <swiper>
    <swiper-slide v-for="(page, index) of pages" :key="index">
      <div class="icon" v-for="item of page" :key='item.id'>
        <div class="icon-img">
          <img class="icon-img-content" :src="item.imgsrc" alt="">
        </div>
        <p class="icon-text">{{item.text}}</p>
      </div>
    </swiper-slide>
  </swiper>
</div>

</template>

<script>
export default {
  name: 'Header-icon',
  computed: {
    pages () {
      const pages = []
      this.imgList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  },
  data () {
    return {
      imgList: [
        {
          id: '0001',
          imgsrc: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          text: '景点门票'
        }, {
          id: '0002',
          imgsrc: 'https://imgs.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
          text: '必游榜单'
        }, {
          id: '0003',
          imgsrc: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/a40ee278d67000f2a29d2e20f6a029b3.png',
          text: '自然风光'
        }, {
          id: '0004',
          imgsrc: 'https://imgs.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
          text: '名胜古迹'
        }, {
          id: '0005',
          imgsrc: 'https://imgs.qunarzz.com/piao/fusion/1803/bd/9f7b9b2b60c1502.png',
          text: '踏青赏花'
        }, {
          id: '0006',
          imgsrc: 'https://imgs.qunarzz.com/piao/fusion/1803/87/20656da0ac042002.png',
          text: '太极洞'
        }, {
          id: '0007',
          imgsrc: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/b6e35d0668c434f6db6d7de07af3a307.png',
          text: '敬亭山'
        }, {
          id: '0008',
          imgsrc: 'https://imgs.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
          text: '桃花潭'
        }, {
          id: '0009',
          imgsrc: 'https://imgs.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
          text: '查济古村'
        }, {
          id: '0010',
          imgsrc: 'https://imgs.qunarzz.com/piao/fusion/1803/87/20656da0ac042002.png',
          text: '水墨汀溪'
        }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .icons
    overflow: hidden
    height: 0
    padding-bottom: 50%
    .icon
      position: relative
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
