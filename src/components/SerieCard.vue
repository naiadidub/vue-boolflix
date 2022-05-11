<template>
    <div class="">
        <p>titolo:{{nome}}</p>
        <p>titolo originale:{{nomeOriginale}}</p>
        <p>lingua: {{linguaOriginale}}</p>
        <p>voto:  {{this.voto}}</p>
        <img :src="'https://image.tmdb.org/t/p/w342' + `${poster}`" alt="">
    </div>
</template>

<script>
export default {
    name: 'SerieCard',
    data(){
        return{
            voto: parseInt(this.votazione , 2)
        }
    },
    props:{
        nome: String,
        nomeOriginale: String,
        linguaOriginale: String,
        votazione: Number,
        poster: String
    }
}
</script>

<style lang="scss" scoped>

</style>