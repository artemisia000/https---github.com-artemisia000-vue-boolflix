<template>
<main>
    
    <div class="col" v-for="item in list" :key="item.id">

         <Card 
       :title="item.title"
       :originalTitle="item.original_title"
       :language="item.original_language"
       :vote="item.vote_average"
    />

  
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

<style>

</style>