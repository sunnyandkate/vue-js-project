<template>
 
 
  <div class="container">
    <div class="main-container">
      <Header :logo="logo" :logoPic="logoPic" />
        <div class="content">
           <router-view/>
        </div>
      <Footer  :logo="logo"/>
    </div>
  </div>
</template>
<script>

import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import logoPic from './assets/images/palmtree.jpg'

export default({
  components:{
    Header,
    Footer
    
  },
  data(){
    return{
      logo:'',
      logoPic:logoPic
    }
  }
 
})
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
 
  color: #2c3e50;
 
}
.container{
  background-color:rgba(247, 168, 180, 0.918);
  height:100vh;
  width:100vw;
  overflow:hidden;
  display:flex;
  justify-content:center;
  align-items:center;
}
.main-container{
  background-color:rgb(173 230 220);
  background-image:linear-gradient(-60deg, rgb(173 230 220) 40%, pink 60%);
  position:relative;
  width:80%;
  height:90%;
  border:1rem solid rgba(229, 236, 236, 0.849);
  box-shadow: 5px 4px 20px 5px #e3576f;
  overflow:scroll;
  
}
  .content{
  min-height:calc(100% - 10rem);
  margin:0;
 padding:2rem;
}


@media(min-width:700px){
  .main-container{
    width:90%;
  }
}




</style>
