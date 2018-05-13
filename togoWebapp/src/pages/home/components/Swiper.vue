<template>
  <div class="wrapper">
    <swiper :options="swiperOption" >
      <swiper-slide v-for="item in swiperList" :key="item.id">
        <img class="swipe-img" :src="item.imgUrl" alt="去哪儿门票" style="opacity: 1;">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/5c/969bfa7af00a2702.jpg_750x200_b99b8e07.jpg'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/15/9250dbc86a456302.jpg_750x200_b423f532.jpg'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/1b/6c766b79e2045102.jpg_750x200_29ad1225.jpg'
      }]
    }
  }
}
</script>

<style lang='less'>
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
