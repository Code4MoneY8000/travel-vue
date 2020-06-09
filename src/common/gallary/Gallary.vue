<template>
    <div class="container" @click='handleShow'>
      <div class="img-container">
        <swiper :options="swiperOptions">
            <swiper-slide v-for="(item, index) of imgs" :key="index">
                <img class="gallary-img" :src="item" alt="">
            </swiper-slide>
            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
      </div>
    </div>
</template>

<script>
export default {
  name: 'Gallary',
  props: {
    imgs: Array
  },
  methods: {
    handleShow () {
      this.$emit('close')
    }
  },
  data () {
    return {
      swiperOptions: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        loop: true,
        observer: true,
        observerParents: true
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
  .container >>> .swiper-container
    overflow: inherit
  .container
    display: flex
    flex-direction: column
    justify-content: center
    position: fixed
    top: 0
    bottom: 0
    left: 0
    right: 0
    background: #000
    .img-container
      width: 100%
      height: 0
      padding-bottom: 100%
      .gallary-img
        width: 100%
      .swiper-pagination
        color: #fff
        bottom: -1rem
</style>
