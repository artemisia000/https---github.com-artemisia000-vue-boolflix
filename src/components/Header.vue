<template>
<header  class="d-flex align-items-center">

    <form >
        <input type="text"
               class="control ms-3"
               placeholder="Search your Movie"
               v-model.trim="searchMovie"
               @keyup.enter="$emit('newMovie', searchMovie)"
         
        >
    </form>

    <button class="btn btn-primary "
            type="submit"
            @click.prevent="$emit('newMovie', searchMovie)"
    >
    Search

    </button>

</header>
  

</template>

<script>
export default {
    name: 'Header',

data(){
    return{
    searchMovie: null,

   };
 },

}

</script>

<style  scoped lang="scss">

header{
    width: 100%;
    height: 70px;

    .btn{
        height: 30px;
        margin: 0 15px;
    }
}


</style>