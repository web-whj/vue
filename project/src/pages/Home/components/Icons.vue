<template>
    <div class="icon">
        <swiper :options="swiperOption">
            <swiper-slide v-for="(page,index) of pages" :key="index">
                <div class="icons" v-for="item of page" :key="item.id">
                    <a :href="item.flherf">
                        <div class="icons-img">
                            <img :src="item.imgUrl" alt="">
                        </div>
                        <p>{{item.text}}</p>
                    </a>
                </div>
            </swiper-slide>
        </swiper>
        <div class="swiper-pagination"  slot="pagination"></div>
    </div>
</template>

<script>
  export default {
    name: "icons",
    data(){
      return{
        swiperOption: {
          pagination:'.swiper-pagination',
          autoplay:false,
        },
        iconsList:[
          {
            id:'0',
            imgUrl:require('@/assets/images/rmjd.png'),
            text:'景点门票',
            flherf:'https://touch.piao.qunar.com/touch/list_%E5%A4%AA%E5%8E%9F_%E6%99%AF%E7%82%B9%E9%97%A8%E7%A5%A8.html?region=%E5%A4%AA%E5%8E%9F&cat=from_area%253Dts_type_nav%2526from_index%253D0%2526from_value%253D%2525E6%252599%2525AF%2525E7%252582%2525B9%2525E9%252597%2525A8%2525E7%2525A5%2525A8%2526dist_city%253D%2525E5%2525A4%2525AA%2525E5%25258E%25259F&isForeign=false&pageSize=10'
          },
          {
            id:'1',
            imgUrl:require('@/assets/images/msgj.png'),
            text:'名胜古迹',
            flherf:'https://touch.piao.qunar.com/touch/list_%E5%A4%AA%E5%8E%9F_%E6%96%87%E5%8C%96%E5%8F%A4%E8%BF%B9.html?region=%E5%A4%AA%E5%8E%9F&cat=from_area%253Dts_type_nav%2526from_index%253D1%2526from_value%253D%2525E5%252590%25258D%2525E8%252583%25259C%2525E5%25258F%2525A4%2525E8%2525BF%2525B9%2526dist_city%253D%2525E5%2525A4%2525AA%2525E5%25258E%25259F&isForeign=false&pageSize=10'
          },
          {
            id:'2',
            imgUrl:require('@/assets/images/yry.png'),
            text:'一日游',
            flherf:'https://touch.piao.qunar.com/touch/list_%E5%A4%AA%E5%8E%9F_%E6%96%87%E5%8C%96%E5%8F%A4%E8%BF%B9.html?region=%E5%A4%AA%E5%8E%9F&cat=from_area%253Dts_type_nav%2526from_index%253D1%2526from_value%253D%2525E5%252590%25258D%2525E8%252583%25259C%2525E5%25258F%2525A4%2525E8%2525BF%2525B9%2526dist_city%253D%2525E5%2525A4%2525AA%2525E5%25258E%25259F&isForeign=false&pageSize=10'
          },
          {
            id:'3',
            imgUrl:require('@/assets/images/bycd.png'),
            text:'必游菜单',
            flherf:'https://touch.piao.qunar.com/touch/list_%E5%A4%AA%E5%8E%9F_%E6%96%87%E5%8C%96%E5%8F%A4%E8%BF%B9.html?region=%E5%A4%AA%E5%8E%9F&cat=from_area%253Dts_type_nav%2526from_index%253D1%2526from_value%253D%2525E5%252590%25258D%2525E8%252583%25259C%2525E5%25258F%2525A4%2525E8%2525BF%2525B9%2526dist_city%253D%2525E5%2525A4%2525AA%2525E5%25258E%25259F&isForeign=false&pageSize=10'
          },
          {
            id:'4',
            imgUrl:require('@/assets/images/rmjd.png'),
            text:'景点门票',
            flherf:'https://touch.piao.qunar.com/touch/list_%E5%A4%AA%E5%8E%9F_%E6%99%AF%E7%82%B9%E9%97%A8%E7%A5%A8.html?region=%E5%A4%AA%E5%8E%9F&cat=from_area%253Dts_type_nav%2526from_index%253D0%2526from_value%253D%2525E6%252599%2525AF%2525E7%252582%2525B9%2525E9%252597%2525A8%2525E7%2525A5%2525A8%2526dist_city%253D%2525E5%2525A4%2525AA%2525E5%25258E%25259F&isForeign=false&pageSize=10'
          },
          {
            id:'5',
            imgUrl:require('@/assets/images/msgj.png'),
            text:'名胜古迹',
            flherf:'https://touch.piao.qunar.com/touch/list_%E5%A4%AA%E5%8E%9F_%E6%96%87%E5%8C%96%E5%8F%A4%E8%BF%B9.html?region=%E5%A4%AA%E5%8E%9F&cat=from_area%253Dts_type_nav%2526from_index%253D1%2526from_value%253D%2525E5%252590%25258D%2525E8%252583%25259C%2525E5%25258F%2525A4%2525E8%2525BF%2525B9%2526dist_city%253D%2525E5%2525A4%2525AA%2525E5%25258E%25259F&isForeign=false&pageSize=10'
          },
          {
            id:'6',
            imgUrl:require('@/assets/images/yry.png'),
            text:'一日游',
            flherf:'https://touch.piao.qunar.com/touch/list_%E5%A4%AA%E5%8E%9F_%E6%96%87%E5%8C%96%E5%8F%A4%E8%BF%B9.html?region=%E5%A4%AA%E5%8E%9F&cat=from_area%253Dts_type_nav%2526from_index%253D1%2526from_value%253D%2525E5%252590%25258D%2525E8%252583%25259C%2525E5%25258F%2525A4%2525E8%2525BF%2525B9%2526dist_city%253D%2525E5%2525A4%2525AA%2525E5%25258E%25259F&isForeign=false&pageSize=10'
          },
          {
            id:'7',
            imgUrl:require('@/assets/images/bycd.png'),
            text:'必游菜单',
            flherf:'https://touch.piao.qunar.com/touch/list_%E5%A4%AA%E5%8E%9F_%E6%96%87%E5%8C%96%E5%8F%A4%E8%BF%B9.html?region=%E5%A4%AA%E5%8E%9F&cat=from_area%253Dts_type_nav%2526from_index%253D1%2526from_value%253D%2525E5%252590%25258D%2525E8%252583%25259C%2525E5%25258F%2525A4%2525E8%2525BF%2525B9%2526dist_city%253D%2525E5%2525A4%2525AA%2525E5%25258E%25259F&isForeign=false&pageSize=10'
          },
          {
            id:'8',
            imgUrl:require('@/assets/images/bycd.png'),
            text:'必游菜单',
            flherf:'https://touch.piao.qunar.com/touch/list_%E5%A4%AA%E5%8E%9F_%E6%96%87%E5%8C%96%E5%8F%A4%E8%BF%B9.html?region=%E5%A4%AA%E5%8E%9F&cat=from_area%253Dts_type_nav%2526from_index%253D1%2526from_value%253D%2525E5%252590%25258D%2525E8%252583%25259C%2525E5%25258F%2525A4%2525E8%2525BF%2525B9%2526dist_city%253D%2525E5%2525A4%2525AA%2525E5%25258E%25259F&isForeign=false&pageSize=10'
          }
        ]
      }
    },
    computed:{
      pages (){
        const pages = [];
        this.iconsList.forEach((item,index)=>{
          const page = Math.floor(index/8);
          if(!pages[page]){
            pages[page]=[];
          }
          pages[page].push(item);
        })
        return pages
      }
    }
  }
</script>

<style lang="scss" scoped>
@import "~css/varibles.scss";
.icon /deep/.swiper-pagination{
    bottom:0;
    width: 100%;
}
.icon /deep/.swiper-pagination-bullet-active{
    background: $bgClock;
    margin: 0 5px;
}
.icon{
    position: relative;
    padding-top: .1rem;
    height: 3.7rem;
    .icons{
        float: left;
        width: 25%;
        padding-top: .1rem;
        .icons-img{
            width: 1.1rem;
            margin: 0 auto;
        }
        p{
            color: #212121;
            font-size: .28rem;
            text-align: center;
            @include ellipsis;
        }
    }
}
</style>