<template>
  <form @submit.prevent="contactSubmit">
    <label>Name: </label>
    <input v-model="name" type="name" required/>
    <label>Username: </label>
    <input v-model="username" type="username" required />
    <div v-if="usernameError">{{ usernameError }}</div>
    <label>Email: </label>
    <input v-model="email" type="email" required/>
   
    <label>Course:</label>
    <select v-model="course">
      <option value="yoga" id="yoga">yoga</option>
      <option value="taichi">tai chi</option>

    </select>
    <div class="item-container">
      <label>items:</label>
      
      <input type="text" v-model="itemList" class="itemInput">
      <button  @click="addItem" class="btn itemBtn">Add</button>
      <div v-for="item in items" :key="item">
        <span @click="deleteItem(item)">{{ item }}</span></div>
      
    </div>
    <div class="acceptBtn">
      <input type="checkbox" v-model="acceptBtn" required>
      <label>accept</label>

    </div>
    <button class="btn submit-btn">submit</button>
  </form>


<p>{{ email }}</p><p>{{ course }}</p><p>{{ acceptBtn }}</p>
</template>
<script>


export default({
    data(){
      return{
        name:'',
        username:'',
        email:'',
        course:'',
        acceptBtn: false,
        itemList:'',
        items:[],
        usernameError:''
        
      }
    },
    methods:{
      addItem(item){
        if(this.itemList){
          if(!this.items.includes(this.itemList)){
            this.items.push(this.itemList)

          }
          
          this.itemList= ''
        }
      },
      deleteItem(item){
          this.items = this.items.filter((yourItem) => {
            return item !== yourItem
          })
      },
      contactSubmit(){
        this.usernameError = this.usernameError.length > 5 ? '' : 'name must be longer'
     
      if(!this.usernameError){
        console.log('name: ' , this.name);
        console.log('username: ', this.username);
        console.log('items: ', this.items);
      }
     
     }
    }

})
</script>
<style scoped>
  form{
    max-width:20rem;
    margin:2rem auto;
    display:flex;
    flex-direction:column;
    justify-content:center;
   
  }
  label{
    color:crimson;
    font-weight:bold;
   font-family: 'New Tegomin', serif;
    margin-bottom:1rem;
  }
  input{
    color:coral;
    background-image:linear-gradient(40deg, rgb(173 230 220) 20%, pink 80%);
   box-shadow:2px 5px 12px rgb(188 156 173);
   padding:.5rem;
    border:1px solid beige;
    outline:none;
    margin-bottom:1rem;
    border-radius:1rem;
  }
  input:focus, select:focus{
    border:1px solid seagreen;
     background-image:linear-gradient(-30deg, rgb(173 230 220) 30%, pink 70%);
  }
  select{
    color:crimson;
    background-image:linear-gradient(40deg, rgb(173 230 220) 20%, pink 80%);
    box-shadow:2px 5px 12px rgb(188 156 173);
    border:none;
    outline:none;
    border-radius:1rem;
    padding:.5rem;
    margin-bottom:1rem;
  
  }
  option{
    color:seagreen;
    background-color:rgb(173 230 220);
  
  }
  .item-container>label{
    display:block;
  }
  .itemInput{
    margin-right:1rem;
  }
  .itemBtn{
    width:25%;
    padding: .2rem;
    text-align:center;
  }
  .acceptBtn{
    margin-bottom:1rem;
  }
  


</style>
