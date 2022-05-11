<template>
  <div>
    <input v-model="userInputText" type="text"> 
    <button v-on:click="searchByText">search</button>
  </div>
</template>

<script>
import state from '../store.js' 
import axios from 'axios'

export default {
  name: 'HeaderContent',
  data(){
    return{
      apiURL: 'https://api.themoviedb.org/3/search/',
      apiURLimg: 'https://image.tmdb.org/t/p/w342',
      apiKey: '489caa8c079cb433d037502378de5b80',
      userInputText: '',
      filmsSearced: [],
      seriesSearced: []
    }
  },
  methods: {
    searchByText(){
      const paramsObj = {
      params: {
        api_key: this.apiKey,
        query: this.userInputText,
        language: 'it-IT' 
      }
    }
      axios.get(this.apiURL + 'movie', paramsObj).then((res)=>{
        this.filmsSearced = (res.data.results);
        state.filmCeracti = this.filmsSearced;
        console.log(state.filmCeracti)
      }).catch((err)=>{
        console.log(err)
      })
      axios.get(this.apiURL + 'tv', paramsObj).then((res)=>{
        this.seriesSearced = (res.data.results);
        state.serieCercate = this.seriesSearced;
        console.log(state.serieCercate)
      }).catch((err)=>{
        console.log(err)
      })
    }
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

<style scoped lang="scss">

</style>
