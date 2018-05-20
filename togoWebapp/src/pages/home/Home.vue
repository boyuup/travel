<template>
  <div>
    <home-header></home-header>
    <swiper :swiperData="swiperData"></swiper>
    <icons :iconsData="iconsData"></icons>
    <lists :listsData="listsData"></lists>
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import Swiper from './components/Swiper'
import Icons from './components/Icons'
import Lists from './components/Lists'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    Swiper,
    Icons,
    Lists
  },
  data () {
    return {
      swiperData: [],
      iconsData: [],
      listsData: {}
    }
  },
  methods: {
    getHomeInfo () {
      axios.get('/static/mock/index.json')
        .then(this.getHomeInfoSuccess)
    },
    getHomeInfoSuccess (res) {
      res = res.data
      if (res.ret && res.data) {
        this.swiperData = res.data.swiperList
        this.iconsData = res.data.iconList
        this.listsData = res.data.listsList
      }
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>

<style scoped>

</style>
