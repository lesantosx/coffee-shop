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
      <span v-for="item in items" :key="item.id">
        <CoffeeCard :item="item"/>
      </span>          
    </div>
  </section>
</template>

<script>

import CoffeeCard from './CoffeeCard.vue'

export default {
  props: {
    items: {
      required: true
    }
  },
  components: {
    CoffeeCard
  },
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
    display: grid;
    grid-template-columns: auto auto auto;
  }
}

</style>