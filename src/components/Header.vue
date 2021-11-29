<template>
<header>

    <form>
        <input type="text"
               class="control ms-3"
               placeholder="Search your Movie"
         
        >
    </form>

    <button class="btn btn-primary "

    >
    Search

    </button>

     


</header>
  

</template>

<script>
export default {
    name: 'Header',

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