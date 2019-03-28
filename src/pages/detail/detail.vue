<template>
  <div>
    <detail-banner :sightName="sightName" :bannerImg="bannerImg" :imgs="galleryImgs"></detail-banner>
    <detail-header></detail-header>
    <div class="content">
      <detail-list :list="list"></detail-list>
    </div>
  </div>
</template>

<script>
import DetailBanner from './components/banner'
import DetailHeader from './components/header'
import DetailList from './components/list'
import axios from 'axios'

export default {
  name: 'detail',
  components: {
    DetailList,
    DetailHeader,
    DetailBanner
  },
  data () {
    return {
      sightName: '',
      bannerImg: '',
      galleryImgs: [],
      list: []
    }
  },
  methods: {
    getInfo () {
      axios.get('/api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.handleGetInfoSucc)
    },
    handleGetInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.galleryImgs = data.gallaryImgs
        this.list = data.categoryList
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
  height :50rem
</style>
