<template>
  <div class="header">
    <div class="header-left"><i class="iconfont">&#xe66f;</i></div>
    <div class="header-input"><i class="iconfont">&#xe619;</i>输入城市/景点/游玩主题</div>
    <div class="header-right">城市<i class="iconfont">&#xe64a;</i></div>
  </div>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style lang="less" scoped>
  @import "~styles/varibles.less";
  .header{
    display:flex;
    line-height: .86rem;
    background:@bgColor;
    color: #fff;
    .header-left{
      width: .64rem;
      float:left;
      i{
        display: block;
        text-align: center;
      }
    }
    .header-input{
      flex:1;
      height:.64rem;
      line-height:.64rem;
      margin-top:.12rem;
      margin-left:.2rem;
      background:#fff;
      border-radius:.1rem;
      color:#ccc;
    }
    .header-right{
      width:1.24rem;
      float:right;
      text-align: center;
    }
  }
</style>
