<template>
  <div class="home">    
    <Header @nav='nav'/>
    <About id='about'/>
    <Gallery/>
    <Service id='service'/>
    <Team class='team' id='team'/>
    <Contact id='contact'/>
    <Footer/>    
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header.vue'
import Gallery from '@/components/Gallery.vue'
import About from '@/components/About.vue'
import Service from '@/components/Service.vue'
import Team from '@/components/Team.vue'
import Contact from '@/components/Contact.vue'
import Footer from '@/components/Footer.vue'


// kick off the polyfill!

export default {
  name: 'Home',
  components: {
    Header,
    Gallery,
    About,
    Service,
    Team,
    Contact,
    Footer
  },
  data() {
    return {
      navigation: ''
    }
  },
  methods: {
    nav(data){
      this.navigation = data;
      document.getElementById(this.navigation).scrollIntoView();
      
    }
  }
}
</script>

<style scoped>

hr{
  margin: auto;
  width:70%;
  color:#987cb9;
  size:1;
}
.team{
  margin-top: 100px;
  margin-bottom: 300px;
}
</style>