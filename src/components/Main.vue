<template>
<main>

<div class="container ">
    <div class="row">
        <div class="col-lg-2" v-for="item in list" :key="item.id">
            
             <Card 
            :title="item.title ? item.title : item.name"
            :originalTitle="item.original_title ? item.original.title : item.original_name"
            :language="item.original_language"
            :vote="item.vote_average"
            :poster="item.poster_path"
            :over="item.overview"
            />
        </div>
    </div>
</div>
   
</main>
  

</template>

<script>
import Card from '@/components/Card.vue';


export default {
    name: 'Main',

       components: {
        Card,
    },
        props: {
            list: Array,  
    },
};


</script>

<style scoped lang="scss">

main{
    height: 100%;
    padding-top: 50px;
    background-color: #1b1b1b;

  
}




</style>