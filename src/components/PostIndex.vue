<template>
    <div class="mt-5" > 
   <table class="table table-bordered">
      <thead>
        <th>Name</th>
        <th>Email</th>
        <th>Action</th>
      </thead>
      <tbody>
        <tr v-for="post in posts" :key="post.id" >
          <td>{{ post.title }}</td>
          <td>{{ post.body }}</td>
           <td>Delete</td>
        </tr>
      </tbody>
    </table>

    </div>
</template>

<script>
import axios from 'axios';
    export default {
        data() {
            return {
              posts:[]  
            }
        },
        methods: {
          
        },
        created(){
          axios.get('https://jsonplaceholder.typicode.com/posts')
          .then(response =>{
              this.posts = response.data
           } )
          .catch(error=>{
              console.log(error);
          })
        }
    }
</script>

<style  scoped>

</style>