<template>
<main>


</main>
  

</template>

<script>
import axios from 'axios';
export default {
    name: 'Main',


data(){
    return{
        listMovie: [],
    };
},

created(){
    this.getMovie();

},

methods: {
    getMovie(){

    axios
        .get('https://api.themoviedb.org/3/search/movie?api_key=01761d48304ba79f4b1135eba2934ae8&query=wes anderson')
        .then(result => {
            console.log(result.data);
            this.listMovie = result.data;
        })
        .catch(error => console.log(error));
    }

  }

};


</script>

<style>

</style>