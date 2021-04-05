<template>
    <header>
        <div class="logo"><img class="logo-img" :src="logoPic"/></div>
      
        <button @click="toggleMenu" class="toggle-btn" :class="{ btnOpenMenu: showMenu }">Menu</button>
        <transition name="fade">
            <nav class="menu" v-if="showMenu" >
                <ul >
                   <li><router-link to="/">Home</router-link></li>
                    <li><router-link :to=" { name: 'About' }">About</router-link></li>
                    <li><router-link :to=" { name: 'Classes' }">Classes</router-link></li>
                    <li><router-link :to="{ name: 'Contact' }">Contact</router-link></li>
                </ul>
            </nav>
        </transition>
    </header>
  
</template>

<script>


export default ({
     props:['logo', 'logoPic'],

   data(){
       return{
           showMenu:false
         
       }
   },
       methods:{
           toggleMenu(){
               this.showMenu = !this.showMenu
            
         }
       }
   
})
</script>
<style>

header{
    background-color:rgb(173, 223, 230);
    background-image:linear-gradient(40deg, rgb(173 230 220) 20%, pink 80%);
    height:5rem;
    position:relative;
}
.logo{
    width:40%;
}
.logo img{
   /*  background-image:url('../assets/images/palmtree.jpg');
    background-size:cover; */
    display:inline-block;
    width:3rem;
    height:3rem;
    margin-top:1rem;
    margin-left:1rem;
    border:2px solid #ffb6c1;
    background-color: rgb(173 230 220);
    border-radius:50%;
    transition: all ease-in-out 2s;
}
.logo:hover .logo-img{
   transform:rotate(180deg);
   margin-left:10rem;
}
 
.menu{
    background-color: #ffb6c19c;
    height: 100vh;
   
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    text-align: center;
    padding: 2rem;
    z-index:2;
   
}
.menu ul li{
    padding:1rem;
    list-style:none;
}
.menu ul li >a{
    color:crimson;
    font-size:2rem;
    text-transform:uppercase;
    text-decoration:none;
}
.toggle-btn{
    border: none;
    padding: .5rem;
    background-color: crimson;
    color: pink;
    font-weight: bold;
     font-family: 'New Tegomin', serif;
    text-transform: uppercase;
    letter-spacing: 1px;
    position: absolute;
    z-index: 22;
    top: 2rem;
    right: 2rem;
    border-top-left-radius: 1rem;
    border-bottom-right-radius: 1rem;
    outline:none;
    cursor:pointer;
}
.btnOpenMenu{
    border-bottom-left-radius: 1rem;
    border-top-right-radius: 1rem;
     border-top-left-radius: 0;
    border-bottom-right-radius: 0;
}
.fade-enter-active{
    animation: fade-in 3s;
}
.fade-leave-active{
    animation: fade-in 2s reverse;
}

 @keyframes fade-in{
    0%{
        opacity:0;
    }
    50%{
        opacity:.5;
    }
    100%{
        opacity:1;
    }
}


</style>