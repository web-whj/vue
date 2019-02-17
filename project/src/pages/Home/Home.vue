<template>
    <div>
        <home-header></home-header>
        <home-swiper></home-swiper>
        <home-icons></home-icons>
        <home-hotlist></home-hotlist>
        <home-love></home-love>
    </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeHotlist from './components/Hotlist'
import HomeLove from './components/Love'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeHotlist,
    HomeLove
  }
}
</script>
<style lang="scss" scoped>
</style>
