<template>

        <div class="card">
            <ul>
                <li>Titolo:{{ title }}</li>
                <li>Titolo originale: {{ originalTitle }}</li>
                <li>Lingua: {{ language }} </li>
                <li>Voto: {{ vote }} </li>
            </ul>
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
    }

};

</script>

<style>

</style>