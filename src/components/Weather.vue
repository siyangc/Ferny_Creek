<template>
  <div class='weather' v-if='typeof weather.main!="undefined"'>
      <div class='weather_item_text'>
        <div class='weather_item'>{{weather.name}} {{temp}}°C</div>
        <div class='weather_item'>{{weather.weather[0].description}}</div>
      </div>
      <div class='weather_item_icon'><img :src= 'icon' alt=""></div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'Weather',
  data() {
      return {
          weather: {},
          url: 'https://api.openweathermap.org/data/2.5/weather?lat=-37.88&lon=145.33&appid=c01881de4575cd8dfe8fcbca2b497e69',
          iconUrl: 'http://openweathermap.org/img/w/',
          icon: '',
          temp: Number,
          color: ''
      }
  },
  methods: {
      changeColor(temp) {
          if(temp<30&&temp>18){
              this.color = 'warm'
          }else if(temp>=30){
              this.color = 'hot'
          }else{
              this.color = 'cold'
          }
      }
  },
  mounted() {
      
      axios.get(this.url).then(res => {
          this.weather = res.data;
          this.icon= this.iconUrl + this.weather.weather[0].icon + '.png';
          this.temp = Math.round(this.weather.main.temp-273.15);
          this.changeColor(this.temp);
          this.$emit('headbg',this.color);
      })
      
        
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
[v-cloak] {
    display: none;
}
.weather {
    display: flex;
    justify-content: flex-end;
    height: 80px;
    width: 600px;
    flex-direction: row;
}
.weather_item_text{
    display: flex;
    flex-direction: column;
}
.weather_item{
    padding-left: 10px;
    padding-right: 10px;
    height: 100%;
    line-height: 40px;
    text-align: center;

}
.weather_item_icon {
    height: 80px;
    width: 80px;
}
img {
    height: 80px;
    width: 80px;
}
</style>
