<template>
  <div class="drink-card">
    <div>
      <img :src="item.image" alt="" class="image-drink"/>      
    </div>
    <div class="details">
      <div class="details-header">
        <span>{{ item.name }}</span>
        <span>${{ item.price }}</span>
      </div>
      <span class="description">{{ item.description }}</span>
      <div class="actions-btn" >   
        <button type="button" class="cart-btn" v-show="false">
          <span class="material-symbols-outlined cart-icon">add_shopping_cart</span>
          Add cart
        </button>    
      </div>
    </div>
  </div>
</template>

<script>

export default {
  props: {
    item: {
      required: true
    }
  },
  components: {},
  created() {}
}

</script>

<style lang="scss" scoped>
@import './../sass/tokens';

.drink-card {
  width: 355px;
  height: 480px;
  background-color: #FFFFFF;
  border-radius: 10px;
  margin-bottom: 10px;
  text-align: center;
  transition: width 0.2s, height 0.5s;
}

.drink-card:hover {
  background-color: $secondary-color;
  opacity: 0.8;
  width: 378px;
  height: 532px;
  
  .description { 
    color: $gray-900;
  }
}

.image-drink {
  width: 200px;
  cursor: pointer;
}

.details {
  padding: 0 15px 0 15px;
}

.details-header {
  display: flex;
  justify-content: space-between;
  font-weight: 700;
  margin-bottom: 15px;
  color: #000000;
}

.description {
  display: block;
  text-align: left;
  justify-items: start;
  color: $gray-800;
  font-weight: 600;
}

.cart-btn {
  width: 321px;
  height: 42px;
  background-color: #FFFFFF;
  color: #240000;
  border: none;
  border-radius: 10px;
  font-weight: 600;
}

.cart-icon {
  font-size: 16px;
  vertical-align: auto;
}

</style>