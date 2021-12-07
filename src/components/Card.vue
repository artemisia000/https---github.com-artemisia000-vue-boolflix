<template>
    
    <div class="box ">
        <div class="card pic">

            <img v-if="poster "
                 :src="`https://image.tmdb.org/t/p/w342${poster}`" 
                 :alt="title"
                 class="poster">

            <img v-else
                 :src="`https://images.unsplash.com/photo-1617396900799-f4ec2b43c7ae?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80`"
                 :alt="title"
                 class="poster1">
        </div>           
        <div class="text">           
            <ul>
                <li>Titolo:{{ title }}</li>
                <li>Titolo originale: {{ originalTitle }}</li>
                <li>Lingua:
                    <img class="flag"
                        v-if="flags.includes(language)" 
                        :src="require(`../assets/${language}.png`)" alt="">   
                </li>
                <li>Voto: {{ vote }}
                <i v-for='(number, index) in Math.ceil(vote/2)' :key="`movie-${index}`" class="fa-regular fa-star star"></i>  
                <i v-for='(number, index) in 5 - Math.ceil(vote/2)' :key="index" class="fa-regular fa-star star"></i>
                </li>
                <li>Trama:{{ over }} </li>
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
        over: String,
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

.box {
    width: 200px;
    height: 300px;
    margin: 15px;



.pic{
        width: 200px;
        border: 2px solid #1b1b1b;
        display: block;
        .poster,
        .poster1{
            width: 100%;
            height: 300px;
            position: absolute;
            top: 0;
            left: 0;
            &:hover{
                display: none;
            }
    
        }

   .text{
    width: 200px;   
    height: 300px;
    background-color: #1b1b1b;
    padding:5px ;
    overflow: scroll;
    &:hover{
        position: relative;
        
       

     
    }

    li{
    list-style: none;
    font-size: 12px;
    color: #ddd;
    background-color: #1b1b1b;
    padding-left: 0;
    margin: 0;    
    }


      
    }

    }

    
 
    }
        .flag{
    width: 30px;
    }

    .star{
        color: yellow;
    }





</style>