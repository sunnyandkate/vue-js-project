<template>
  <form>
    <label>Name: </label>
    <input v-model="name" type="name" required/>
    <label>Email: </label>
    <input v-model="email" type="email" required/>
   
    <label>Course:</label>
    <select v-model="course">
      <option value="yoga" id="yoga">yoga</option>
      <option value="taichi">tai chi</option>

    </select>
    <div class="item-container">
      <label>items:</label>
      
      <input type="text" v-model="tempSkills" class="itemInput">
      <button  @click="addItem" class="btn itemBtn">Add</button>
      <div v-for="item in items" :key="item">{{ item }}</div>
    </div>
    <div class="acceptBtn">
      <input type="checkbox" v-model="acceptBtn" required>
      <label>accept</label>

    </div>
  </form>


<p>{{ email }}</p><p>{{ course }}</p><p>{{ acceptBtn }}</p>
</template>
<script>


export default({
    data(){
      return{
        name:'',
        email:'',
        course:'',
        acceptBtn: false,
        tempSkills:'',
        items:[]
      }
    },
    methods:{
      addItem(item){
        if(this.tempSkills){
          this.items.push(this.tempSkills)
          this.tempSkills = ''
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
  


</style>
