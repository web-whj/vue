<template>
    <div>
        <home-header></home-header>
        <home-swiper :list="swiperList"></home-swiper>
        <home-icons :iconsList="iconsList"></home-icons>
        <home-hotlist :hotList="hotList"></home-hotlist>
        <home-love :loveList="loveList"></home-love>
    </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeHotlist from './components/Hotlist'
import HomeLove from './components/Love'
import axios from 'axios'
import { mapState } from 'vuex'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeHotlist,
    HomeLove
  },
  data (){
    return{
      lastCity:[],
      swiperList:[],
      iconsList:[],
      hotList:[],
      loveList:[]
    }
  },
  computed:{
      ...mapState(['city'])
  },
  methods:{
    getHomeInfo(){
      axios.get('/api/index.json?city='+this.city).then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc(res){
      res= res.data;
      if(res.ret && res.data) {
        const data = res.data;
        this.swiperList = data.swiperList;
        this.iconsList = data.iconsList;
        this.hotList = data.hotList;
        this.loveList= data.loveList;
      }
    }
  },
  mounted(){
    this.lastCity=this.city;
    this.getHomeInfo()
  },
  activated(){
    if(this.lastCity !== this.city){
      this.lastCity=this.city;
      this.getHomeInfo();
    }
  }
}
</script>
<style lang="scss" scoped>
</style>
