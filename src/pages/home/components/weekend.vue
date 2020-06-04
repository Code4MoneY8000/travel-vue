<template>
  <div>
      <div class="title">周末去哪儿</div>
      <div class="item" v-for='item of itemList' :key='item.id'>
        <div class="item-icon">
          <img class="item-img" :src="item.imgsrc" alt="">
        </div>
        <div class="item-info">
          <div class="item-name">
            <p>{{item.name}}</p>
          </div>
          <div class="item-desc">
            <p>{{item.desc}}</p>
          </div>
        </div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'Headerweekend',
  data () {
    return {
      itemList: [
        {
          id: '0001',
          imgsrc: 'https://imgs.qunarzz.com/sight/source/1511/fd/0285e145e82233.jpg_r_640x214_b5f10121.jpg',
          name: '歙县旅游',
          desc: '山水相依的江南小城'
        }, {
          id: '0002',
          imgsrc: 'https://imgs.qunarzz.com/sight/source/1511/fd/0285e145e82233.jpg_r_640x214_b5f10121.jpg',
          name: '歙县旅游',
          desc: '山水相依的江南小城'
        }, {
          id: '0003',
          imgsrc: 'https://imgs.qunarzz.com/sight/source/1511/fd/0285e145e82233.jpg_r_640x214_b5f10121.jpg',
          name: '歙县旅游',
          desc: '山水相依的江南小城'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
.title
  line-height: .8rem
  background: #eee
  text-indent: .2rem
  margin-top: .2rem
.item
  .item-icon
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 33.9%
    .item-img
      width: 100%
  .item-info
    padding: .1rem
    text-indent: .2rem
    .item-name
      line-height: .54rem
      font-size: .32rem
    .item-desc
      line-height: .4rem
      color: #ccc
</style>
