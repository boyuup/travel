<template>
  <div class="wrapper" v-if="isShow">
    <swiper :options="swiperOption" >
      <swiper-slide v-for="item in swiperData" :key="item.id">
        <img class="swipe-img" :src="item.imgUrl" alt="" style="opacity: 1;">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    swiperData: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      }
    }
  },
  computed: {
    isShow () {
      return this.swiperData.length
    }
  }
}
</script>

<style lang='less'>
  .swiper-pagination-bullets{
    bottom:.03rem!important;
  }
  .swiper-pagination-bullet-active{
    background: #fff!important;
  }
  .wrapper{
    width: 100%;
    height: 0;
    padding-bottom:26.63%;
    overflow: hidden;
    background: #eaeaea;
  }
  .swipe-img{
    width: 100%;
  }
</style>
