<template>
    <div class="list" ref="wrapper">
        <div>
            <div class="area">
                <div class="title">当前城市</div>
                <div class="button-box">
                    <div class="button-list">
                        <router-link to="/">
                            <div class="button">{{this.Scity}}</div>
                        </router-link>
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title">热门城市</div>
                <div class="button-box">
                    <div class="button-list" v-for="item of hostcity" :key="item.code" @click="handleCityClick(item.name)">
                        <div class="button">{{item.name}}</div>
                    </div>
                </div>
            </div>
            <div class="area" v-for="item of city" :ref="item.initial">
                <div class="title">{{item.initial}}</div>
                <ul class="item-list" v-for="items of item.list">
                    <li class="item" @click="handleCityClick(items.name)">{{items.name}}</li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
  import Bscroll from 'better-scroll'
  import { mapState,mapMutations } from 'vuex'
  export default {
    name: "list",
    props:{
      hostcity:Array,
      city:Array,
      letter:String,
    },
    methods:{
      handleCityClick (city) {
        this.changeCity(city);
        this.$router.push('/');
      },
      ...mapMutations(['changeCity']),
    },
    computed:{
      ...mapState({
        Scity:'city'
      })
    },
    watch:{
      letter () {
        if(this.letter){
          const  ele = this.$refs[this.letter][0];
          this.scroll.scrollToElement(ele)
        }
      }
    },
    mounted (){
      this.scroll= new Bscroll(this.$refs.wrapper,{ click: true });
    }
  }
</script>

<style lang="scss" scoped>
    .list{
        overflow: hidden;
        position: absolute;
        top: 1.58rem;
        left: 0;
        right: 0;
        bottom: 0;
        z-index: -1;
        .area{
            .title{
                line-height: .44rem;
                background: #eee;
                padding-left: .2rem;
                color: #666666;
                font-size: .26rem;
            }
            .button-box{
                padding: .1rem;
                overflow: hidden;
                padding: .1rem .6rem .1rem .1rem;
                .button-list{
                    float: left;
                    width: 33.33%;
                    .button{
                        font-size: 0.28rem;
                        text-align: center;
                        margin: .2rem;
                        border: .02rem solid #ccc;
                    }
                }
            }
            .item-list{
                .item{
                    line-height: .76rem;
                    font-size: .24rem;
                    padding-left: .2rem;
                    border-bottom: 0.02rem solid #ccc;
                }
            }
        }
    }


</style>