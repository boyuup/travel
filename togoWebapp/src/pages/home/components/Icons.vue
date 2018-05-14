<template>
  <div class="icons">
    <swiper >
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
  data () {
    return {
      lists: [{
        id: '0',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1703/5a/612ae0fee636d202.jpg',
        desc: '北京'
      }, {
        id: '1',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1804/53/f7c33a4412d59e02.png',
        desc: '上海'
      }, {
        id: '2',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1704/fd/7b733d3656f4d002.png',
        desc: '八达岭长城'
      }, {
        id: '3',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1804/53/f7c33a4412d59e02.png',
        desc: '上海'
      }, {
        id: '4',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1606/72/65b06c9a1158de9a.png',
        desc: '古北水镇'
      }, {
        id: '5',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1804/53/f7c33a4412d59e02.png',
        desc: '上海'
      }, {
        id: '6',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1804/53/f7c33a4412d59e02.png',
        desc: '上海'
      }, {
        id: '7',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1606/b3/0249b48a69aaf49a.png',
        desc: '上海'
      }, {
        id: '8',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1804/53/f7c33a4412d59e02.png',
        desc: '上海'
      }, {
        id: '9',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1804/53/f7c33a4412d59e02.png',
        desc: '上海'
      }]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.lists.forEach((item, index) => {
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
