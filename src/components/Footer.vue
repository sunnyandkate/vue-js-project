<template>
    <footer>
        <div class="logo">{{ logo }}</div>
        <a href="mailto:info@sunnyandkate.com">info@sunnyandkate.com</a>
    </footer>
</template>

<script>


export default ({
    props:['logo'],
   data(){
       return{

       }
   }
})
</script>
<style>

footer{
    background-color:lightblue;
     background-image:linear-gradient(-70deg, pink 20%, rgb(173 230 220) 80%);
    height:5rem;
    position:relative;
    bottom:0;
    right:0;
    left:0;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
}
footer .logo{
    background-image:url('../assets/images/palmtree.jpg');
    background-size:cover;
    width:3rem;
    height:3rem;
    margin-top:.5rem;
    margin-bottom:.5rem;
    border-radius:50%;
   
}
footer > a{
    text-decoration: none;
    color:seagreen;
}
footer>a:hover{
    color:hotpink;
}

</style>