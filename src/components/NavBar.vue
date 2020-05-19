<template>
  <div class='nav'>

    <div class='menu'>
      <div class='menu-item' @click="about">{{$t("NavBar.About")}}</div>
      <div class='menu-item' @click="service">{{$t("NavBar.Service")}}</div>
      <div class='menu-item' @click="team">{{$t("NavBar.Team")}}</div>
      <div class='menu-item' @click="contact">{{$t("NavBar.Contact")}}</div>
      <div class='menu-item dropdown'>
        {{$t("NavBar.Language")}}
        <div class='dropdown-item'>
            <a class='dropdown-content' @click="changeZh">中文</a>
            <a class='dropdown-content' @click="changeEn">English</a>
        </div>        
      </div>
    </div>

    <div class='menu-m' >      
      <button class="menu-btn dropdown" @click="changeButtonColor" ref="close">Menu</button>
      <transition name='dropdown-item-m'><div class='dropdown-item-m' v-show="show">
          <a class="dropdown-content-m" @click="about">{{$t("NavBar.About")}}</a>
          <a class='dropdown-content-m' @click="service">{{$t("NavBar.Service")}}</a>
          <a class='dropdown-content-m' @click="team">{{$t("NavBar.Team")}}</a>
          <a class='dropdown-content-m' @click="contact">{{$t("NavBar.Contact")}}</a>
          <a class='dropdown-content-m' @click="$i18n.locale=['zh','en'].filter(x=>x!=$i18n.locale)[0]">{{$t("NavBar.Lang")}}</a>
      </div></transition>      
    </div>

  </div>    
</template>

<script>
export default {
  name: 'NavBar',
  data(){
    return {
      show: false,
      nav:''
    }
  },
  methods: {
    changeButtonColor(){
      this.show = !this.show;
      if(this.show == true){
        this.$refs.close.setAttribute('class','menu-btn-active');
      }else{
        this.$refs.close.setAttribute('class','menu-btn');
      }
    },
    about(){
      this.nav = 'about';
      this.$emit('nav',this.nav);      
    },
    service(){
      this.nav = 'service';
      this.$emit('nav',this.nav)
    },
    team(){
      this.nav = 'team';
      this.$emit('nav',this.nav)
    },
    contact(){
      this.nav = 'contact';
      this.$emit('nav',this.nav)
    },
    changeZh(){
      this.$i18n.locale = 'zh'
    },
    changeEn(){
      this.$i18n.locale = 'en'
    }
  },
  mounted() {
    document.addEventListener('click', (e) => {
        if (!this.$refs.close.contains(e.target)) {
          this.show = false;
          this.$refs.close.setAttribute('class','menu-btn');
        }
  })
}
};
</script>

<style scoped>

.nav {
  width: 100%;
  background-color: hsla(0, 0%, 100%, 0.4);
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
  height: 40px;
  display: flex;
  justify-content: flex-end;
}
.menu{
  display: flex;  
}
.menu-item{
  min-width: 100px;
  cursor: pointer;
  padding-left: 10px;
  padding-right: 10px;
  text-align: center;
  line-height: 40px;
  font-size: 12px;
}
.menu-item:hover{
  background-color: hsla(0, 0%, 100%, 0.4);
  box-shadow: 0 1px 2px rgba(0,0,0,.13);    
}
.menu-m{
  height: 40px;
}
.menu-btn{
  height: 40px;
  width: 100px;
  border: none;
  z-index: 10;
  outline:none;
  background-color: gray;
  border-radius: 5%;
}
.menu-btn-active{
  height: 40px;
  width: 100px;
  border: none;
  z-index: 10;
  outline:none;
  background-color: #1c1c1d42;
  border-radius: 5%;
  color:#ffffff;
}

.dropdown{
  display: inline-block;
  position: relative;
  user-select:none;
}
.dropdown-item{
  visibility: hidden;
  height: 0px;
  opacity:0;
  position: absolute;
  right: 0px;
  width: 100px;
  background-color: #f9f9f9;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  display: flex;
  flex-direction: column;
}
.dropdown-item-m{
  position: absolute;
  top: 40px;
  right: 0px;
  background-color: #f9f9f9;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  width: 200px;
  display: flex;
  flex-direction: column;
  user-select:none;
}
.dropdown:hover .dropdown-item{
  visibility: visible;
  height: 80px;
  transition: 0.5s;
  opacity:1;
}

.dropdown-content:hover{
  background-color: rgba(10, 10, 235, 0.514);
}
.dropdown-content-m:hover{
  background-color: rgba(10, 10, 235, 0.514);
}
.dropdown-content-m{
  height: 60px;
  line-height: 60px;
  min-width: 200px;
  text-align: left;  
  padding-left:10px;
}
.dropdown-item-m-enter-active {
  transition: all 1s ease;
}
.dropdown-item-m-enter{
  transform: translateX(10px);
  opacity: 0;
  width: 0px;
}
@media (max-width: 500px) {
  .menu {
    display: none;
  }
  .menu-item{
    display: none;
  }
}
  
@media (min-width: 501px) {
  .menu-m{
    display: none;
  }
}
</style>