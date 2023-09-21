<template>
  <div>
    <Header />
    <Menu :items="items"/>
  </div>  
</template>

<script>

import Header from './components/Header.vue'
import Menu from './components/Menu.vue'
import api from './api.json'

export default {
  name: 'App',
  components: {
    Header,
    Menu
  },
  data() {
    return {
      items: [],
      coffees: [],
      iceDrinks: []
    }
  }, 
  created() {   
    this.items = api
    
  }
}
</script>

<style lang="scss">
@import './sass/tokens';

#app {
  background-color: $background-primary;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  min-height: 100vh;
}
</style>
