<template>
  <div class="header" :class='bg_color'>
    <NavBar @nav='nav' class='navbar-pos'/>
    <Weather @headbg = 'changeColor' class='weather-pos'/>
  </div>
</template>

<script>
import NavBar from '@/components/NavBar.vue'
import Weather from '@/components/Weather.vue'

export default {
  name: 'Header',
  components: {
      NavBar,
      Weather
  },
  data() {
    return {
      bg_color: String
    }
  },
  methods: {
    changeColor(data){
      this.bg_color = data;
    },
    nav(data){
      this.$emit('nav',data)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header{

    height: 120px;
    position: relative;
}
.cold{
  background-image: linear-gradient(to bottom right, rgb(223, 242, 245), rgb(116, 157, 245));
}
.warm{
  background-image: linear-gradient(to bottom right, rgb(223, 242, 245), rgb(224, 183, 67));
}
.hot{
  background-image: linear-gradient(to bottom right, rgb(223, 242, 245), rgb(167, 28, 28));
}
.weather-pos{
  top: 40px;
  right: 0px;
  position: absolute;
}
.navbar-pos{
  position: fixed;
  z-index: 100;
}
</style>
