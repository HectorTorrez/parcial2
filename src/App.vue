<template>

     <table class="table">
  <thead>
    <tr>
      <th scope="col">Id</th>
      <th scope="col">Titulo</th>
      <th scope="col">Descripcion</th>
     
    </tr>
  </thead>
  <tbody>
    <!---aqui tendrias que poner un for para que te agregue los datos del api --->
     <!---<tr v-for="(usuario, index) in usuarios" v-bind:key="usuario"> --->

      <td> {{categories.id}}</td>
      <td>{{categories.title}}</td>
      <td>{{categories.id}}</td>
     
   
      

  </tbody>
    </table>
</template>



<script>
import axios from 'axios'
export default {
    name: 'App',
     data(){
        return{
            
            categories:[],
        }
    },
    created() {
      //Aqui pondrias el link que ya sabes cual es
        axios.get('http://127.0.0.1:8000/api/hobbies') // endpoint API Laravel
        .then(response=>{
            this.categories = response.data
        })
        .catch(e=>{
            this.errors.push(e)
        })
    },
    
}
</script>