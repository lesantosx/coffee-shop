<template>
  <section id="menu">    
    <div class="header d-flex">
      <span class="text-header">Our <span class="text-custom">Coffees</span></span>
      <span class="filters">
        <template v-for="filter in filters" :key="filter">
          <span 
            class="text-default"           
            :class="filter.active ? 'text-hover' : ''"
            @click="filterCoffee(filter.id)"
          >
          {{ filter.text }}
        </span>
        </template>        
      </span>
    </div>

    <div class="coffees">
      <template v-for="coffee in coffees" :key="coffee">
        <CoffeeCard :item="coffee" />
      </template>     
    </div>  

    <div class="text-center mt-4">
      <span class="see-more">See more</span>
    </div>

    <div class="header d-flex drinks-section">
      <span class="text-header">Our <span class="text-custom">Drinks</span></span>
    </div>

    <div class="drinks">
      <template v-for="drink in drinks" :key="drink">
        <IceDrinkCard :item="drink" />
      </template>      
    </div>
  </section>
</template>

<script>

import CoffeeCard from './CoffeeCard.vue'
import IceDrinkCard from './IceDrinkCard.vue'

export default {
  props: {
    coffees: {
      required: true
    },
    drinks: {
      required: true
    }
  },
  components: {
    CoffeeCard,
    IceDrinkCard,
  },
  data() {
    return {
      filters: [
        {id: 1, text: 'All Coffee', active: true},
        {id: 2, text: 'Hot Coffee', active: false},
        {id: 3, text: 'Ice Coffee', active: false}
      ]
    }
  },
  methods: {
    filterCoffee(id){
      this.filters.forEach((filter) => {
        if(filter.id === id) {
          filter.active = true
          return
        }
        filter.active = false
      })
    }
  }
}

</script>

<style lang="scss" scoped>
@import './../sass/tokens';

#menu {
  padding: 200px 250px 0 250px;

  .header {    
    justify-content: space-between;
  }

  .text-header {
    font-size: 32px;
    font-weight: 700;
    color: $primary-color;
  }

  .text-custom {
    border-bottom: 3px solid $secondary-color;
  }

  .filters {    
    span {
      font-size: 18px;
      font-weight: 700;
      color: $primary-color;
      padding-right: 20px;
      cursor: pointer;
    }

    .text-hover {
      --c:linear-gradient(#AD6D2F 0 0);
  
      padding-bottom: .15em;
      background: var(--c), var(--c);
      background-size: .3em .1em;
      background-position:50% 100%;
      background-repeat: no-repeat;
      transition: .3s linear, background-size .3s .2s linear;
    }

    .text-hover:hover {
      background-size: 40% .1em;
      background-position: 5% 100%, 60% 100%;
    }
  }

  .coffees {
    margin-top: 100px;
    display: grid;
    grid-template-columns: auto auto auto;
  }

  .see-more {
    font-size: 24px;
    font-weight: 700;
    cursor: pointer;
    --c:linear-gradient(#AD6D2F 0 0);
  
    padding-bottom: .15em;
    background: var(--c), var(--c);
    background-size: .3em .1em;
    background-position:50% 100%;
    background-repeat: no-repeat;
    transition: .3s linear, background-size .3s .2s linear;
  }

  .see-more:hover {
    background-size: 40% .1em;
    background-position: 10% 100%, 90% 100%;
  }

  .drinks-section {
    margin-top: 100px;
  }

  .drinks {
    display: grid;
    grid-template-columns: auto auto auto;
    margin-top: 100px;
  }
}

</style>