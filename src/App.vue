<template>
  <div id="app">
    <Header  @newMovie="searchChar"/>

    <Main />
  
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
    return{
        listMovie: [],
        searchText: '',
    };
},

computed: {
  filterChar(){
    console.log('computed');

    if(this.searchText === ''){
      return this.listMovie;

    }
    return  this.listMovie.filter(item => {
      return item.results.title.tolowerCase().includes(this.searchText.tolowerCase())
    });

  },
},

created(){
    this.getMovie();

},

methods: {
    getMovie(){

    axios
        .get('https://api.themoviedb.org/3/search/movie', {

          params: {
            api_key: '01761d48304ba79f4b1135eba2934ae8',
            query: 'Wes Anderson',
          },
        })
        .then(result => {
            console.log(result.data);
            this.listMovie = result.data;
        })
        .catch(error => console.log(error));
    },

    searchChar(text){
      console.log(text);
      this.searchText = text;

    },
  },

};




</script>

<style lang="scss">

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

</style>
