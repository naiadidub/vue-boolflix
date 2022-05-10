<template>
  <div id="app">
    <HeaderContent/>
    <MainContent/>
  </div>
</template>

<script>
import HeaderContent from './components/HeaderContent.vue'
import MainContent from './components/MainContent.vue'
export default {
  name: 'App',
  components: {
    HeaderContent,
    MainContent
  }
}
</script>

<style lang="scss">
#app {
  
}
</style>
