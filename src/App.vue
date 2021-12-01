<template>
  <div id="app">
    <Header  @search="searchChar"/>

    <Main :list="listMovie"/>
    <Main  :list="listTV"/>
  
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Main from '@/components/Main.vue';
import axios from 'axios';


export default {
  name: 'App',
  components: {
    Header,
    Main,
  },

  data(){
    return {
      listMovie: [],
      listTV: [],
    };
  },
  

methods: {
 
      searchChar(searchText) {
        console.log(searchText);

        if(this.searchText !== '') {

        axios.get('https://api.themoviedb.org/3/search/movie', {

          params: {
            api_key: '01761d48304ba79f4b1135eba2934ae8',
            query: searchText,
          },
        })

        .then(result => {
            console.log(result.data);
            this.listMovie = result.data.results;
        })
        .catch(error => console.log(error));


        axios.get('https://api.themoviedb.org/3/search/tv', {

          params: {
            api_key: '01761d48304ba79f4b1135eba2934ae8',
            query: searchText,
          },
        })

        .then(result => {
            console.log(result.data);
            this.listTV = result.data.results;
        })
        .catch(error => console.log(error));

       }
   
  },
 },
};

</script>

<style lang="scss">

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Cabin', sans-serif;
  font-family: 'Cabin Sketch', cursive;
  font-family: 'Outfit', sans-serif;
  font-family: 'Varela Round', sans-serif;
 
}
  

</style>