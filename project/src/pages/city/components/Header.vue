<template>
    <div class="header">
        <router-link to="/">
            <span class="iconfont">&#xe607;</span>
        </router-link>
        <h1>城市选择</h1>
    </div>
</template>

<script>
  export default {
    name: "CityHeader"
  }
</script>

<style lang="scss" scoped>
    @import "~css/varibles.scss";
    .header{
        height: .86rem;
        line-height: .86rem;
        position: relative;
        background: $bgClock;
        span{
            left: 0;
            top: 0;
            width: .8rem;
            height: .88rem;
            line-height: .88rem;
            position: absolute;
            font-size: .36rem;
            color: #fff;
            text-align: center;
        }
        h1{
            margin: 0 1rem;
            line-height: .88rem;
            font-size: .32rem;
            text-align: center;
            color: #fff;
            @include ellipsis;
        }
    }

</style>