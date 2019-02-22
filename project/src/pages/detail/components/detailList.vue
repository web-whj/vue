<template>
    <div>
        <div class="listbox" v-for="item of list">
            <div class="list">
                {{item.title}}
            </div>
            <div v-if="item.children" class="list-children">
                <detail-list :list="item.children"></detail-list>
            </div>

        </div>

    </div>
</template>

<script>
  export default {
    name: "DetailList",
    props:{
      list:Array
    },
    data (){
      return{
        abs:true,
      }
    }
  }
</script>

<style lang="scss" scoped>
.list{
    padding: 0 .2rem;
    font-size: .32rem;
    line-height: .8rem;
}

.list-children{
    padding: 0 .2rem;
    font-size: .24rem;
    color: #00bcd4;
}
</style>