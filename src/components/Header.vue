<template>
<header class="container-fluid">
    <div class="row">
        <div class="col nav">
            <div class="box">
                <ul>
                    <li><a href=""><img src="https://fontmeme.com/permalink/211201/c072857f28ffed69c9266a55183f4c20.png" alt=""></a></li>
                    <li><a href="">Home</a></li>
                    <li><a href="">Serie TV</a></li>
                    <li><a href="">Film</a></li>
                    <li><a href="">Originali</a></li>
                    <li><a href="">Aggiunti di recente</a></li>
                    <li><a href="">La mia lista</a></li>
                </ul>
            </div>

            <div class="box">
          
                <input type="text"
                       class="control ms-3"
                       placeholder="Search your Movie"
                       v-model.trim="searchText"
                       @keyup.enter="$emit('search', searchText)" 
                >
                <button class="btn  "
                        type="submit"
                        @click="$emit('search', searchText)"
                >
                  search
                </button>
                
            </div>
        </div>
    </div>    
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
    background-color: #000;
    
}

    .nav{
        display: flex;
        justify-content: space-between;
        height: 70px;
    }

    ul{
        display: flex;
        list-style: none;
        line-height: 70px;
        font-size: 15px;

        a{
            text-decoration: none;
            color: #fff;
            margin: 0 20px;

            &:hover{
                color: #dc1a28;
            }

            img{
                width: 120px;
            }
          
        }

    }

    .box{
        height: 70px;
        display: flex;
        align-items: center;
        

         .control{
        width: 100px;
        border: transparent;
        background-color:#000 ;
        color: #fff;
        border-bottom: 3px solid #1b1b1b;
        outline: none;
        &:hover{
            border: transparent;
            border-bottom: 2px solid #dc1a28;
        }  
    }

    .btn{
        height: 30px;
        margin: 0 15px;
    }


    }

  


</style>