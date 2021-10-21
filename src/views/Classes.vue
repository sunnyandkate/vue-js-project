<template>
     <h1>classes</h1>
     <div v-for="item in classes" :key="item.id">
         <h2>{{ item.name }}</h2>
     </div>
  
</template>

<script>
export default {

    data(){
        return{
            classes:[
                {
                    name:'yoga',
                    id: 1,
                    details:'something'
                },
                {
                    name:'tai chi',
                    id: 2,
                    details:'something'
                }
            ]
        }
    }

}
</script>

<style>

</style>