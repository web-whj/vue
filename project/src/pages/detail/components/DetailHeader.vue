<template>
    <div>
        <div class="headerBox" v-show="ShowTitle" :style="titleOpacity">
            <router-link to="/" class="headerBox-left">
                <p class="iconfont">&#xe607;</p>
            </router-link>
            <h1 class="title" >{{ids}}</h1>
        </div>
    </div>
</template>

<script>
  export default {
    name: "detail-header",
    props:{
      ids:String
    },
    data () {
      return{
        ShowTitle:false,
        titleOpacity:{
          opacity:0
        }
      }
    },
    methods:{
      handleScroll (){
        const scrollTop = document.documentElement.scrollTop;
        if(scrollTop > 80){
          let opacity = scrollTop/200;
          opacity = opacity > 1 ? 1 :opacity
          this.titleOpacity={
            opacity
          }
          this.ShowTitle = true;
        }else{
          this.ShowTitle = false;
        }
      }
    },
    mounted (){
      window.addEventListener('scroll',this.handleScroll)
    },
    beforeDestroy () {
      window.removeEventListener('scroll',this.handleScroll)
    }

  }
</script>

<style lang="scss" scoped>
.headerBox{
    position: fixed;
    width: 100%;
    top: 0;
    left: 0;
    display: block;
    opacity: 1;
    height: .88rem;
    background: #00bcd4;
    .headerBox-left{
        color: #fff;
        width: .8rem;
        height: .88rem;
        line-height: .88rem;
        text-align: center;
        float: left;
    }
    .title{
        overflow: hidden;
        margin: 0 1rem;
        line-height: .88rem;
        white-space: nowrap;
        text-overflow: ellipsis;
        font-size: .32rem;
        text-align: center;
        color: #fff;
    }
}
</style>