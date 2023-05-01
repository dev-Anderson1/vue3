<script>
  import http from '@/services/http.js'
 export default {


    data(){
      return{
          users:[],
      }
    }, 
    async mounted(){
      try {
          const {data} = await http.get('http://localhost:8000/api/users');
          this.users = data;
      } catch (error) {
        console.log(error)
      }
    }, 
    update(){
      console.log('update');
    }
  }


</script>

<template>
    <h2>Lista de Usuarios</h2>
    <ul>
      <li v-for="user in users" :key="user.id"> {{ user.firstName }}</li>
    </ul>
</template>

<style scoped>


</style>
