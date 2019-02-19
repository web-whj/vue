<template>
    <div class="hotlist">
        <div class="title">
            <div class="title-left">
                <div class="title-img">
                    <img src="@/assets/images/huo.png" alt="">
                </div>
                <span>本周热门榜单</span>
            </div>
            <div class="title-right">
                全部榜单
                <span class="iconfont">&#xe603;</span>
            </div>
        </div>
        <ul class="list">
            <li v-for="item of hotList" :key="item.id">
                <a href="">
                    <div class="ph">
                        <!--<img src="./static/images/one.png" alt="">-->
                    </div>
                    <div class="hotimg">
                        <img :src="item.imgUrl" alt="">
                    </div>
                    <div class="hotname">{{item.name}}</div>
                    <div class="hotmoney">
                        <span>¥<em>{{item.money}}</em></span>
                        <em>起</em>
                    </div>
                </a>
            </li>
        </ul>
    </div>
</template>

<script>
  export default {
    name: "hotlist",
    props:{
      hotList:Array
    },
  }
</script>

<style lang="scss" scoped>
    .hotlist{
        margin-top: .2rem;
        .title{
            padding: .24rem 0 .26rem;
            overflow: hidden;
            .title-left{
                float: left;
                .title-img{
                    width: .3rem;
                    height: .3rem;
                    margin-left: .2rem;
                    float: left;
                }
                span{
                    margin-left: .08rem;
                    color: #212121;
                    font-size: .32rem;
                    float: right;
                }
            }
            .title-right{
                color: #616161;
                font-size: .24rem;
                line-height: .28rem;
                float: right;
                margin-right: .32rem;
            }
        }
        .list {
            padding: 0 .24rem;
            overflow-x: scroll;
            white-space: nowrap;
            li{
                position: relative;
                padding: .06rem 0 .2rem;
                width: 2rem;
                display: inline-block;
                .ph{
                    position: absolute;
                    top: 0;
                    left: 0;
                    z-index: 1;
                    overflow: hidden;
                    width: .84rem;
                    height: .4rem;
                }
                .hotimg{
                    width: 2rem;
                }
                .hotname{
                    margin-top: .12rem;
                    color: #212121;
                    font-size: .24rem;
                    line-height: .32rem;
                    text-align: center;
                }
                .hotmoney{
                    color: #616161;
                    font-size: .24rem;
                    line-height: .36rem;
                    text-align: center;
                    span{
                        color:#ff8300;
                    }
                }
            }
            li:not(:first-child){
                margin-left: .12rem;
            }

        }
    }
</style>