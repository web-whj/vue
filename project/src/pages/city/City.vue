<template>
    <div>
        <city-header></city-header>
        <city-seach :city="city"></city-seach>
        <city-list :hostcity="hostcity" :city="city" :letter="letter"></city-list>
        <city-alphabet :city="city" @change="handleLetterClick"></city-alphabet>
    </div>
</template>

<script>
import CityHeader from "./components/Header"
import CitySeach from "./components/Seach"
import CityList from "./components/list"
import CityAlphabet from "./components/Alphabet"
import axios from 'axios'
export default {
  name: "city",
  data (){
    return{
      hostcity:[],
      city:[],
      letter:''
    }
  },
  components:{
    CityHeader,
    CitySeach,
    CityList,
    CityAlphabet
  },
  methods:{
    getCityInfo(){
      axios.get('/api/city.json').then(this.getCityInfoSuss)
    },
    getCityInfoSuss(res){
      res = res.data;
      if(res.ret && res.hostcity && res.city){
        this.hostcity = res.hostcity;
        this.city = res.city;
      }
    },
    handleLetterClick(letter){
        this.letter = letter
    }
  },
  mounted (){
    this.getCityInfo();
  }
}
</script>

<style scoped>

</style>