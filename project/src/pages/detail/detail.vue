<template>
    <div>
        <detail-header :ids="ids"></detail-header>
        <detail-banner></detail-banner>
        <div class="con">
            <detail-list :list="list">

            </detail-list>
        </div>
    </div>
</template>

<script>
  import axios from 'axios'
  import detailBanner from  './components/header'
  import detailHeader from './components/DetailHeader'
  import detailList from './components/detailList'
  export default {
    name: "detail",
    components:{
      detailBanner,
      detailHeader,
      detailList
    },
    data (){
      return{
        ids:this.$route.params.id,
        ShowGallary:false,
        list:[
          {
            title:"成人票",
            children:[{
              title:"成人女票"
            },
            {
              title:"成人男票"
            }]
          },
          {
            "title":"学生票",
            children:[{
              title:"学生女票"
            },
              {
                title:"学生男票"
              },{
                title:"学生不要票"
              }]
          },
          {
            "title":"儿童票"
          },
          {
            "title":"特惠票"
          }
        ]
      }
    },
    methods:{
      getDetailInfo (){
        axios.get('/api/detail.json',{
          params:{
            id:this.$route.params.id
          }
        }).then(this.handleGetDataSucc)
      },
      handleGetDataSucc(res){
        res = res.data;
      }
    },
    mounted(){
      this.getDetailInfo();
    }
  }
</script>

<style scoped>
.con{
    height: 50rem;
}
</style>