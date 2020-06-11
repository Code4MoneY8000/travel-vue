<template>
  <div>
    <detail-banner></detail-banner>
    <detail-header></detail-header>
    <div class="content">
      <detail-list :list='list'></detail-list>
    </div>
  </div>
</template>

<script>
import DetailBanner from './components/detail-banner'
import DetailHeader from './components/detail-header'
import DetailList from './components/detail-list'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      list: [{
        title: '学生票',
        children: [{
          title: '小学生票',
          children: [{
            title: '中小学生票'
          }]
        }]
      }, {
        title: '老人票',
        children: [{
          title: '老老年人票',
          children: [{
            title: '中老年人票'
          }]
        }]
      }, {
        title: '成人票',
        children: [{
          title: '老成年人票',
          children: [{
            title: '中年人票'
          }]
        }]
      }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
.content
  height: 50rem
</style>
