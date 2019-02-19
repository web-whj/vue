<template>
    <ul class="list">
        <li class="item" v-for="item of city" @click="handleLetterClick" v-bind:class='{active:item.initial==chag}'>{{item.initial}}</li>
    </ul>
</template>

<script>
  export default {
    name: "alphabet",
    props:{
      city:Array,
      letter:String
    },
    data (){
      return{
        chag:'',
      }
    },
    methods:{
      handleLetterClick (e){
        this.$emit('change',e.target.innerText);
      }
    }
  }
</script>

<style lang="scss" scoped>
    @import "~css/varibles.scss";
.list{
    display: flex;
    flex-direction: column;
    justify-content: center;
    position: absolute;
    top:1.58rem;
    right: 0;
    bottom: 0;
    width: .4rem ;
    .item{
        color: $bgClock;
        font-size: 0.28rem;
        line-height: .44rem;
        text-align: center;
    }
    .active{
        /*font-size: 0.32rem;*/
        /*color:#ccc;*/
    }
}
</style>