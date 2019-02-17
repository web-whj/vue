<template>
    <div class="imagesBox">
        <swiper :options="swiperOption">
            <!-- slides -->
            <swiper-slide v-for="item of swiperList" :key="item.id">
                <img :src="item.imgUrl" alt="">
            </swiper-slide>
            <!-- Optional controls -->
            <div class="swiper-pagination"  slot="pagination"></div>
            <!--<div class="swiper-button-prev" slot="button-prev"></div>-->
            <!--<div class="swiper-button-next" slot="button-next"></div>-->
            <!--<div class="swiper-scrollbar"   slot="scrollbar"></div>-->
        </swiper>
    </div>
</template>

<script>
export default {
  name: 'HelloSwiper',
  data() {
    return {
      swiperOption: {
        pagination:'.swiper-pagination',
        loop:true,
        autoplay:3000,
      },
      pagination :{
        el: '.swiper-pagination',
        clickable :true,
      },
      swiperList:[
        {
          id:'0',
          imgUrl:require('@/assets/images/lunbo.jpg')
        },
        {
          id:'1',
          imgUrl:require('@/assets/images/lunbo2.jpg')
        }
      ]
    }
  }
}
</script>
<style lang="scss" scoped>
    .imagesBox /deep/.swiper-pagination-bullets{
        bottom: 0;
    }
    .imagesBox /deep/ .swiper-pagination-bullet-active{
        background: #fff;
    }
    .imagesBox{
        overflow: hidden;
        width: 100%;
        height: 0;
        padding-bottom: 26.67%;
    }
</style>
