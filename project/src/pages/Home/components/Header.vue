<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont">&#xe607;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe613;</span>
      输入城市/景点/游玩主题
    </div>
    <div class="header-right">
      城市
      <span class="iconfont">&#xe604;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>
<style  lang="scss" scoped>
  @import "~css/varibles.scss";
  .header{
    font-size: 0.30rem;
    display: flex;
    height: 0.86rem;
    line-height: .86rem;
    background: $bgClock;
    color: #fff;
    .header-left{
      width: .64rem;
      float: left;
      box-sizing: border-box;
      .iconfont{
        text-align: center;
      }
    }
    .header-input{
      flex:1;
      height: .64rem;
      line-height: .64rem;
      margin-top: .12rem;
      margin-left: .2rem;
      background: #fff;
      border-radius: .1rem;
      color:#ccc;
      .iconfont{
        padding-left: 0.12rem;
      }
    }
    .header-right{
      width: 1.24rem;
      text-align: center;
      float: right;
      .iconfont{
        margin-left: -.04rem;
        font-size: 0.24rem;
      }
    }
  }
</style>
