<template>
    <div>
        <div>
            <FilmCard v-for="(film, index) in MySearch" :key="index"
            :titolo="film.title"
            :titoloOriginale="film.original_title"
            :lingua="film.original_language"
            :voto="film.vote_average"
            :poster="film.poster_path"
            />
        </div>
        <div>
            <SerieCard v-for="(serie, index) in MySearchSeries" :key="index"
            :nome="serie.name"
            :nomeOriginale="serie.original_name"
            :linguaOriginale="serie.original_language"
            :votazione="serie.vote_average"
            :poster="serie.poster_path"
            />
        </div>
    </div>
</template>

<script>
import state from '../store'
import FilmCard from './FilmCard.vue'
import SerieCard from './SerieCard.vue'
export default {
    name: 'MainContent',
    components:{
        FilmCard,
        SerieCard
    },
    computed: {
        MySearch(){
            return state.filmCeracti
        },
        MySearchSeries(){
            return state.serieCercate
        }
    }
    
}
</script>

<style>

</style>