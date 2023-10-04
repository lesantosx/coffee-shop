<template>
  <div>
    <Header />
    <Menu :coffees="coffees" :drinks="iceDrinks" />
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
      coffees: [],
      iceDrinks: []
    }
  }, 
  created() {   
    this.coffees = api.coffees   
    this.iceDrinks = api.drinks 
  }
}
</script>

<style lang="scss">
@import './sass/tokens';

#app {
  background-color: $background-primary;
  font-family: $font-family;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  min-height: 100vh;
}
</style>
