<template>
 
        
         <div class="flex-container">
          <img :src="beachPic" class="beachPic" alt="beach" />
          <div class="col-right"> 
            <p class="text">Yoga at the beach</p>
            <Buttons />
          </div>
         </div>
         <hr>
     
</template>

<script>
import Buttons from '../components/Buttons.vue'
import beachPic from '../assets/images/maha.jpg'

export default {
  components:{
    Buttons
  },
  data(){
    return{
      beachPic: beachPic
    }
  }
}
</script>
<style scoped>

.flex-container{
  display:flex;
  flex-direction: column;
  justify-content:center;
  align-items:center;
  text-align:center;
  margin-top:2rem;
}
.beachPic{
  width:60%;
  margin-left:2rem;
  border-top-left-radius:1.5rem;
  border-top-right-radius:1rem;
  border-bottom-left-radius:1rem;
  border-bottom-right-radius:1.5rem;
  box-shadow: 2px 2px 20px #ade6dc;
}
.beachPic:hover{
  border-top-left-radius:1rem;
  border-top-right-radius:1.5rem;
  border-bottom-left-radius:1.5rem;
  border-bottom-right-radius:1rem;
}
.text{
  color:rgb(255, 0, 119);
  font-size:1.5rem;
  letter-spacing:1px;
  margin-bottom:3rem;
}
.text:hover{
  color:silver;
  text-shadow:5px 2px 20px lightpink;
  
  
}
hr{
  margin-top:5rem;
  background-image:linear-gradient(to right, rgb(173 230 220) 20%, pink);
  border:none;
  border-radius:2rem;
  height:.1rem;
  
}

@media(min-width:700px){
  
  .flex-container{
    flex-direction: row;
    justify-content:space-around;
  }
  .beachPic{
    width:30%;
  }
}





</style>
