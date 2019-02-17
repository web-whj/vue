<template>
    <div>
        <home-header></home-header>
        <home-swiper></home-swiper>
        <div class="sj">这是首页</div>
    </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper
  }
}
</script>
<style lang="scss" scoped>
</style>
