<template>
  <div class="icons">
    <swiper  :options="swiperOption" >
      <swiper-slide v-for="(page,index) in pages" :key="index">
        <div class="icon" v-for="item in page" :key="item.id">
          <div class="icon-img">
            <img class="mpm-iconbar-img" alt="" :src="item.imgUrl">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'Icons',
  props: {
    iconsData: Array
  },
  data () {
    return {
      swiperOption: {
        loop: false,
        outplay: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconsData.forEach((item, index) => {
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

<style lang='less' scoped>
  .icons{
    overflow: hidden;
    height:0;
    padding-bottom: 50%;
    background-color: #fff;
    .icon{
      float: left;
      width:25%;
      padding-bottom: 25%;
      position: relative;
      .icon-img{
        position: absolute;
        left:0;
        right:0;
        top:0;
        bottom:.44rem;
        padding: .1rem;
        img{
          display: block;
          margin: 0 auto;
          height: 100%;
        }
      }
      .icon-desc{
        position: absolute;
        left: 0;
        right:0;
        bottom:0;
        height:.44rem;
        line-height:.44rem;
        color:#333;
        text-align: center;
        font-size: .24rem;
      }
    }
  }
</style>
