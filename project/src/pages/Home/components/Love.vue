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
                <a :href="item.hotUrl">
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
    </div>
</template>

<script>
  export default {
    name: "love",
    data (){
      return{
        hotList:[
          {
            id:'0',
            hotUrl:'http://touch.piao.qunar.com/touch/detail.htm?id=193401&from=as_recommend_sight',
            imgUrl:require('@/assets/images/cwzy.png'),
            name:'采薇庄园滑雪场',
            money:'30',
            hotName:'598条评论',
            style:'84%',
            area:'榆次区'
          },
          {
            id:'1',
            hotUrl:'http://touch.piao.qunar.com/touch/detail.htm?id=193401&from=as_recommend_sight',
            imgUrl:require('@/assets/images/qlgz.jpg'),
            name:'青龙古镇',
            money:'3.5',
            hotName:'609条评论',
            style:'94%',
            area:'太原区'
          },
          {
            id:'2',
            hotUrl:'http://touch.piao.qunar.com/touch/detail.htm?id=193401&from=as_recommend_sight',
            imgUrl:require('@/assets/images/tyshx.jpg'),
            name:'台骀山滑世界',
            money:'54',
            hotName:'413条评论',
            style:'62%',
            area:'太原区'
          },
          {
            id:'3',
            hotUrl:'http://touch.piao.qunar.com/touch/detail.htm?id=193401&from=as_recommend_sight',
            imgUrl:require('@/assets/images/cwzy.png'),
            name:'采薇庄园滑雪场',
            money:'30',hotName:'609条评论',
            style:'94%',
            area:'太原区'
          },
          {
            id:'4',
            hotUrl:'http://touch.piao.qunar.com/touch/detail.htm?id=193401&from=as_recommend_sight',
            imgUrl:require('@/assets/images/qlgz.jpg'),
            name:'青龙古镇',
            money:'3.5',hotName:'413条评论',
            style:'62%',
            area:'太原区'
          },
          {
            id:'5',
            hotUrl:'http://touch.piao.qunar.com/touch/detail.htm?id=193401&from=as_recommend_sight',
            imgUrl:require('@/assets/images/tyshx.jpg'),
            name:'台骀山滑世界',
            money:'54',
            hotName:'609条评论',
            style:'94%',
            area:'太原区'
          },
          {
            id:'6',
            hotUrl:'http://touch.piao.qunar.com/touch/detail.htm?id=193401&from=as_recommend_sight',
            imgUrl:require('@/assets/images/cwzy.png'),
            name:'采薇庄园滑雪场',
            money:'30',
            hotName:'609条评论',
            style:'94%',
            area:'太原区'
          },
          {
            id:'7',
            hotUrl:'http://touch.piao.qunar.com/touch/detail.htm?id=193401&from=as_recommend_sight',
            imgUrl:require('@/assets/images/qlgz.jpg'),
            name:'青龙古镇',
            money:'3.5',
            hotName:'609条评论',
            style:'94%',
            area:'太原区'
          },
          {
            id:'8',
            hotUrl:'http://touch.piao.qunar.com/touch/detail.htm?id=193401&from=as_recommend_sight',
            imgUrl:require('@/assets/images/tyshx.jpg'),
            name:'台骀山滑世界',
            money:'54',
            hotName:'229条评论',
            style:'44%',
            area:'小店区'
          },
        ],
      }
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
    }
</style>