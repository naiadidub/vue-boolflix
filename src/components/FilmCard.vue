<template>
    <div class="">
        <p>titolo:{{titolo}}</p>
        <p>titolo originale:{{titoloOriginale}}</p>
        <p>lingua: {{lingua}}</p>
        <p>voto: {{voto}}</p>
        <img :src="'https://image.tmdb.org/t/p/w342' + `${poster}`" alt="">
    </div>
</template>

<script>
export default {
    name: 'FilmCard',
    props:{
        titolo: String,
        titoloOriginale: String,
        lingua: String,
        voto: Number,
        poster: String
    }
}
</script>

<style lang="scss" scoped>

</style>