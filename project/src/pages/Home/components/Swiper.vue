<template>
    <div class="imagesBox">
        <swiper :options="swiperOption" v-if="showSwiper">
            <!-- slides -->
            <swiper-slide v-for="item of list" :key="item.id">
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
  props:{
    list:Array
  },
  data() {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: 3000,
      }
    }
  },
  computed:{
    showSwiper(){
      return this.list.length
    }
  }
}
</script>
<style lang="scss" scoped>
    .imagesBox /deep/.swiper-pagination-bullets{
        bottom: 0;
    }
    .imagesBox /deep/ .swiper-pagination-bullet-active{
        background: #ff1715;
    }
    .imagesBox{
        overflow: hidden;
        width: 100%;
        height: 0;
        padding-bottom: 42.14%;
    }
</style>
