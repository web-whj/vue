<template>
    <div>
        <div class="search">
            <input  v-model="keyword" type="text" class="search-input" placeholder="输入城市名或拼音" />
        </div>
        <div class="search-con" ref="search" v-show="keyword">
            <ul>
                <li class="search-item" v-for="item of list" @click="handleCityClick(item.name)">{{item.name}}</li>
                <li class="search-item" v-show="hasNoData">没有找到匹配数据</li>
            </ul>
        </div>
    </div>


</template>

<script>
  import Bscroll from 'better-scroll'
  export default {
    name: "seach",
    props:{
      city:Array
    },
    data (){
      return{
        keyword:'',
        list:[],
        timer:null
      }
    },
    computed:{
      hasNoData () {
        return !this.list.length
      }
    },
    watch: {
      keyword () {
        if(this.timer){
          clearTimeout(this.timer);
        }
        if(!this.keyword){
            this.list=[];
            return
        }
        this.timer = setTimeout( () => {
          const result = [];
          for(let i in this.city){
            this.city[i].list.forEach((value)=>{
                if(value.pinyin.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1){
                    result.push(value)
                }
              this.list = result;
            })
          }
        },100)
      }
    },
    mounted () {
      this.scroll = new Bscroll(this.$refs.search,{click:true});
    },
    methods:{
      handleCityClick(city){
        this.$store.commit('changeCity',city);
        this.$router.push('/')
      }
    }
  }
</script>

<style lang="scss" scoped>
    @import "~css/varibles.scss";
    .search{
        height: .72rem;
        padding: 0 .1rem;
        background: $bgClock;
        .search-input{
            width: 100%;
            height: .62rem;
            padding: 0 .1rem;
            line-height: .62rem;
            text-align: center;
            border-radius: .06rem;
            background: #fff;
            color: #666;
            box-sizing: border-box;
        }
    }
    .search-con{
        overflow: hidden;
        position: absolute;
        top: 1.58rem;
        left: 0;
        right: 0;
        bottom: 0;
        background: #ccc;
        font-size: 0.24rem;
        z-index:1;
        .search-item{
            line-height: .62rem;
            padding-left: .2rem;
            color: #666;
            background: #fff;
            border-bottom: .02rem solid #ccc;
        }
    }
</style>