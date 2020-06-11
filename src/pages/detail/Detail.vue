<template>
  <div>
    <detail-banner :sightName='sightName' :bannerImg='bannerImg' :imgs='gallaryImgs'></detail-banner>
    <detail-header></detail-header>
    <div class="content">
      <detail-list :list='categoryList'></detail-list>
    </div>
  </div>
</template>

<script>
import DetailBanner from './components/detail-banner'
import DetailHeader from './components/detail-header'
import DetailList from './components/detail-list'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImgs: [],
      categoryList: []
    }
  },
  methods: {
    getInfo () {
      axios.get('/api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.getInfoSucc)
    },
    getInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.gallaryImgs = data.gallaryImgs
        this.categoryList = data.categoryList
      }
    }
  },
  mounted () {
    this.getInfo()
  }
}
</script>

<style lang="stylus" scoped>
.content
  height: 50rem
</style>
