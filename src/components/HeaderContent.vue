<template>
  <div>
    <input v-model="userInputText" type="text"> 
    <button v-on:click="searchByText">search</button>
    <ul>
      <li v-for="(film, index) in filmsSearced" :key="index">{{film.original_title}}</li>
    </ul>
  </div>
</template>

<script>

import axios from 'axios'

export default {
  name: 'HeaderContent',
  data(){
    return{
      apiURL: 'https://api.themoviedb.org/3/search/',
      apiKey: '489caa8c079cb433d037502378de5b80',
      userInputText: '',
      filmsSearced: []
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
        this.filmsSearced = (res.data.results)
        console.log(this.filmsSearced)
      }).catch((err)=>{
        console.log(err)
      })
    }
  }
 
}
</script>

<style scoped lang="scss">

</style>
