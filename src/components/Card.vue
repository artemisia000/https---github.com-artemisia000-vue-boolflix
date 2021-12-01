<template>
    
        <div class="card ">
            <img v-if="poster "
                 :src="`https://image.tmdb.org/t/p/w342${poster}`" 
                 :alt="title">

            <img v-else
                 :src="`https://images.unsplash.com/photo-1617396900799-f4ec2b43c7ae?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80`"
                 :alt="title">  

                 <div class="text">
                      <ul>
                <li>Titolo:{{ title }}</li>
                <li>Titolo originale: {{ originalTitle }}</li>
                <li>Lingua:
                    <img class="flag"
                         v-if="flags.includes(language)" 
                         :src="require(`../assets/${language}.png`)" alt="">   
                </li>
                <li>Voto: {{ vote }} </li>
            </ul>


                 </div>



   
        </div>
</template>

<script>
export default {
    name: 'Card',

    props: {
        title: String,
        originalTitle: String,
        language: String,
        vote: Number,
        poster: String,
    },

    data() {
        return {
          flags: ['it', 'en'],
          posters: [],
       
        }
    },

};

</script>

<style scoped lang="scss">

.card {
    width: 200px;
    justify-content: flex-start;
    border: #1b1b1b;
    
    li{
        list-style: none;
        font-size: 15px;
        color: #ddd;
        background-color: #1b1b1b;
        padding: 0;
        margin: 0;
        
    }

    .text{
      height: 300px;
      background-color: #1b1b1b;
    }

    img{
        width: 200px;
    }

    .flag{
        width: 30px;
    }
}

</style>