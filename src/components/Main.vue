<template>
<main>
    
    <div class="col" v-for="item in list" :key="item.id">
  <!--      <div class="card">
            <ul>
                <li>Titolo:{{ item.title }}</li>
                <li>Titolo originale: {{ item.original_title }}</li>
                <li>Lingua: {{ item.original_language }} </li>
                <li>Voto: {{ item.vote_average }} </li>
            </ul>
        </div>
        -->
    </div>

    <Card 
       :title="item.title"
       :originalTitle="item.original_title"
       :language="item.original_language"
       :vote="item.vote_average"
    />

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