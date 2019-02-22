<template>
    <div class="banner">
        <div @click="handerBannerClick">
            <img src="http://img1.qunarzz.com/sight/p0/1504/53/534e10a3cac61f25.water.jpg_600x330_3b237a37.jpg" alt="">
        </div>
        <fade-gallary>
            <common-gallary v-show="ShowGallary" @close="handerBannerClose"></common-gallary>
        </fade-gallary>
    </div>
</template>

<script>
  import commonGallary from 'common/Gallary/Gallary'
  import FadeGallary from 'common/fade/GallaryFade'
  export default {
    name: "detailBanner",
    components:{
      commonGallary,
      FadeGallary
    },
    data (){
      return{
        ShowGallary:false
      }
    },
    methods:{
      handerBannerClick(){
        this.ShowGallary = true
      },
      handerBannerClose(){
        this.ShowGallary = false
      }
    }
  }
</script>

<style scoped>
    .banner{
    }
</style>