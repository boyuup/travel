<template>
  <div class="lists"  v-if="isShow">
    <div class="title border-bottom"><h3>{{listsData.title}}</h3></div>
    <ul>
      <li class="border-bottom" v-for="item in listsData.list" :key="item.id">
        <div class="content_left">
          <div class="imgBox"><img :src="item.imgUrl" alt=""></div>
        </div>
        <div class="content_right">
          <h4>{{item.title}}</h4>
          <div class="tagBox">
            <span>醉美花海</span><span>醉美花海</span>
          </div>
          <div class="evaluate">
            <div class="starlevel">{{item.starlevel}}</div>
            <span>{{item.evaluateLength}}评论</span>
          </div>
          <div class="site">{{item.site}}</div>
          <div class="price">
            <span>￥</span>
            <span>{{item.price}}</span>
            <span>起</span>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Lists',
  props: {
    listsData: Object
  },
  computed: {
    isShow () {
      let boo = false
      if (this.listsData.list) {
        boo = true
      }
      return boo
    }
  }
}
</script>

<style lang='less' scoped>
  .lists{
    background-color: #fff;
  }
  .title{
    padding: .3rem 0;
    margin-top:.2rem;
    text-align: center;
    font-size:.28rem;
    h3{
      display: inline-block;
      font-weight: normal;
      font-size: .36rem;
      line-height:.36rem;
      position:relative;
      &:after{
        content: "";
        display:block;
        width: .2rem;
        height: .01rem;
        position: absolute;
        left: -.4rem;
        top:.18rem;
        background-color:#9e9e9e ;
      }
      &:before{
        content: "";
        display:block;
        width: .2rem;
        height: .01rem;
        position: absolute;
        right: -.4rem;
        top:.18rem;
        background-color:#9e9e9e ;
      }
    }
  }
  li{
    padding:.2rem .2rem .2rem 0;
    margin-left: .2rem;
    &:last-child{
      &:before{
        display: none;
      }
    }
    &:after{
      content: "";
      display: block;
      height:0;
      clear: both;
      visibility: hidden;
    }
  }
  .content_left{
    float: left;
    .imgBox{
      width: 2rem;
      height:2rem;
      img{
        display: block;
        width: 100%;
        height:100%;
      }
    }
  }
  .content_right{
    height: 2rem;
    overflow: hidden;
    margin-left: 2.2rem;
    position: relative;
    h4{
      font-weight: normal;
      font-size: .32rem;
      line-height: .44rem;
    }
    .tagBox{
      span{
        font-size: .26rem;
        line-height: .50rem;
        color: #00afc7;
        padding: 0 .1rem;
      }
    }
    .evaluate{
      margin-top: .26rem;
      .starlevel{
        display: inline-block;
        height: .28rem;
        width: .9rem;
        background-color: #ffb436;
        vertical-align: middle;
      }
      span{
        color: #9e9e9e;
        font-size: .24rem;
        line-height:.24rem;
        vertical-align: middle;
      }
    }
    .site{
      position: absolute;
      bottom:0;
      font-size: .24rem;
      color: #9e9e9e;
    }
    .price{
      position: absolute;
      bottom:0;
      right:0;
      span{
        color: #ff8300;
        &:nth-child(1){
          font-size: .22rem;
        }
        &:nth-child(2){
          font-size: .4rem;
        }
        &:nth-child(3){
          color: #9e9e9e;
          font-size: .24rem;
        }
      }
    }
  }
</style>
