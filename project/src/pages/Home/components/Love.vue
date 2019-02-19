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
            <li v-for="item of loveList" :key="item.id">
                <a href="">
                    <div class="hotimg">
                        <img :src="item.imgUrl" alt="">
                    </div>
                    <div class="hotMessage">
                        <div class="hotname">{{item.name}}</div>
                        <div class="hotX">
                            <span class="star">
                                <strong class="iconfont" :style="{width:item.style}">&#xe600;&#xe600;&#xe600;&#xe600;&#xe600;</strong>
                                <span class="iconfont stars">&#xe600;&#xe600;&#xe600;&#xe600;&#xe600;</span>
                            </span>
                            <span class="hotComment">{{item.hotName}}</span>
                        </div>
                        <div class="hotmoney">
                            <div class="moneys">
                                <span>¥<em>{{item.money}}</em></span>
                                <em>起</em>
                            </div>
                            <div class="area">
                                {{item.area}}
                            </div>
                        </div>
                    </div>
                </a>
            </li>
        </ul>
        <div class="more">
            <a href="">
                查看所有产品
            </a>
        </div>
    </div>
</template>

<script>
  export default {
    name: "love",
    props:{
      loveList:Array
    }
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
            li{
                padding: .06rem 0 .2rem;
                width: 100%;
                display: inline-block;
                .hotimg{
                    width: 2rem;
                    float: left;
                }
                .hotMessage{
                    padding-left: .22rem;
                    overflow: hidden;
                    .hotname{
                        margin-top: .26rem;
                        height: .44rem;
                        color: #212121;
                        font-size: .32rem;
                        line-height: .44rem;
                    }
                    .hotX{
                        margin-top: .14rem;
                        height: .34rem;
                        position: relative;
                        display: flex;
                        .star{
                            width: 1.5rem;
                            height: .28rem;
                            line-height: .28rem;
                            font-size: .28rem;
                            letter-spacing: .02rem;
                            transform: scale(.83);
                            strong{
                                overflow: hidden;
                                position: absolute;
                                top: .04rem;
                                left: 0;
                                height: .28rem;
                                z-index: 2;
                                color: #ffb436;
                            }
                            .stars{
                                overflow: hidden;
                                position: absolute;
                                top: .04rem;
                                left: 0;
                                height: .28rem;
                                z-index: 1;
                                color: #ccc;
                            }
                        }
                        .hotComment{
                            color: #616161;
                            font-size: .24rem;
                            margin-left: .5rem;
                        }
                    }
                    .hotmoney{
                        margin-top: .22rem;
                        color: #616161;
                        font-size: .24rem;
                        .moneys{
                            float: left;
                            span{
                                font-size: .4rem;
                                color:#ff8300;
                            }
                        }
                        .area{
                            float: right;
                        }
                    }
                }

            }
            li:not(:first-child){
                margin-left: .12rem;
            }

        }
        .more{
            padding: .2rem 0;
            line-height: .4rem;
            text-align: center;
            a{
                color: #00afc7;
                font-size: .28rem;
            }
        }
    }
</style>