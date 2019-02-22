<template>
    <div class="banner" @click="handerBannerChange">
        <div class="wrapper">
            <swiper :options="swiperOptions">
                <swiper-slide>
                    <img class="gallary-img" src="http://img1.qunarzz.com/sight/p0/1504/fb/fb926848a35019a3.water.jpg" alt="">
                </swiper-slide>
                <swiper-slide>
                    <img src="http://img1.qunarzz.com/sight/p0/1504/eb/eb9db2292f5268c4.water.jpg_r_800x800_3f307013.jpg" alt="">
                </swiper-slide>
                <div class="swiper-pagination"  slot="pagination"></div>
            </swiper>
        </div>
    </div>   
</template>

<script>
  export default {
    name: "gallary",
    data () {
      return{
        swiperOptions:{
          pagination:".swiper-pagination",
          paginationType : 'fraction',
          observeParents:true,
          observer:true,
        }
      }
    },
    methods:{
      handerBannerChange(){
        this.$emit('close')
      }
    }
  }
</script>

<style lang="scss" scoped>
    .banner /deep/ .swiper-container{
        overflow: inherit;
    }
.banner{
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    background: #000000;
    position: fixed;
    left: 0;
    top: 0;
    bottom: 0;
    right: 0;
    .wrapper{
        color: #fff;
        .swiper-pagination{
            font-size: 0.24rem;
            bottom: -1rem;
        }
    }
}
</style>