<template>
  <section id="menu">    
    <div class="header d-flex">
      <span class="text-header">Our <span class="text-custom">Coffees</span></span>
      <span class="filters">
        <span class="text-default">All Coffee</span>
        <span class="text-default">Hot Coffee</span>
        <span class="text-default">Ice Coffee</span>
      </span>
    </div>

    <div class="coffees">
      <Carousel v-bind="settings" :breakpoints="breakpoints">
        <Slide v-for="coffee in coffees" :key="coffee">
          <div class="carousel__item">
            <CoffeeCard :item="coffee"/>
          </div>
        </Slide>

        <template #addons>
          <Pagination /> 
          <Navigation />
        </template>
      </Carousel>
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
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'
import 'vue3-carousel/dist/carousel.css'

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
    Carousel,
    Slide,
    Pagination,
    Navigation
  },
  data() {
    return {
      settings: {
        itemsToShow: 3,
        snapAlign: 'center',
      },
      breakpoints: {
        // 700px and up
        700: {
          itemsToShow: 2,
          snapAlign: 'center',
        },
        // 1024 and up
        1024: {
          itemsToShow: 3,
          snapAlign: 'start',
        },
      },
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
  }

  .coffees {
    margin-top: 100px;
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