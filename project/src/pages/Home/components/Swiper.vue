<template>
    <div class="imagesBox">
        <swiper :options="swiperOption">
            <!-- slides -->
            <swiper-slide>
                <img src="@/assets/images/lunbo.jpg" alt="">
            </swiper-slide>
            <swiper-slide>
                <img src="@/assets/images/lunbo2.jpg" alt="">
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
        pagination:'.swiper-pagination'
      }
    }
  }
}
</script>
<style lang="scss" scoped>
.imagesBox{
    overflow: hidden;
    width: 100%;
    height: 0;
    padding-bottom: 26.67%;
}
</style>
