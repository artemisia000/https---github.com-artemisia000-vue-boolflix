<template>
<header  class="d-flex align-items-center">

    <form >
        <input type="text"
               class="control ms-3"
               placeholder="Search your Movie"
               v-model.trim="searchText"
               @keyup.enter="$emit('search', searchText)"
         
        >
    </form>

    <button class="btn btn-primary "
            type="submit"
            @click="$emit('search', searchText)"
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
    searchText: '',

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