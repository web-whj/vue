<template>
    <div class="icon">
        <swiper :options="swiperOption">
            <swiper-slide v-for="(page,index) of pages" :key="index">
                <div class="icons" v-for="item of page" :key="item.id">
                    <a href="">
                        <div class="icons-img">
                            <img :src="item.imgUrl" alt="">
                        </div>
                        <p>{{item.text}}</p>
                    </a>
                </div>
            </swiper-slide>
        </swiper>
        <div class="swiper-pagination swiper-2"  slot="pagination"></div>
    </div>
</template>

<script>
  export default {
    name: "icons",
    props:{
      iconsList:Array
    },
    data(){
      return{
        swiperOption: {
          pagination:'.swiper-2',
          autoplay:false,
        }
      }
    },
    computed:{
      pages (){
        const pages = [];
        this.iconsList.forEach((item,index)=>{
          const page = Math.floor(index/8);
          if(!pages[page]){
            pages[page]=[];
          }
          pages[page].push(item);
        })
        return pages
      }
    }
  }
</script>

<style lang="scss" scoped>
@import "~css/varibles.scss";
.icon /deep/.swiper-pagination{
    bottom:0;
    width: 100%;
}
.icon /deep/.swiper-pagination-bullet-active{
    background: $bgClock;
    margin: 0 5px;
}
.icon{
    position: relative;
    padding-top: .1rem;
    height: 3.7rem;
    .icons{
        float: left;
        width: 25%;
        padding-top: .1rem;
        .icons-img{
            width: 1.1rem;
            margin: 0 auto;
        }
        p{
            color: #212121;
            font-size: .28rem;
            text-align: center;
            @include ellipsis;
        }
    }
}
</style>