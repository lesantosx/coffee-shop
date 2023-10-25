<template>
  <div 
    class="drink-card" 
    v-on:mouseover="mouseover"
    v-on:mouseleave="mouseleave"
  >
    <div>
      <img :src="item.image" alt="" class="image-drink"/>      
    </div>
    <div class="details">
      <div class="details-header">
        <span>{{ item.name }}</span>
        <span>${{ item.price }}</span>
      </div>
      <span class="description">{{ item.description }}</span>
      <div class="actions-btn">   
        <button type="button" class="cart-btn" v-if="showBtn == true">
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
  data() {
    return {
      showBtn: false
    }
  },
  components: {},
  created() {},
  methods: {
    mouseover() {
      this.showBtn = true
    },    
    mouseleave() {
      this.showBtn = false
    }
  }
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
  transition: width 0.2s, height 0.5s ease;
  cursor: pointer;

  img {
    transition: transform .5s ease;
  }
}

.drink-card:hover {
  background-color: $secondary-color;
  opacity: 0.8;
  width: 378px;
  height: 532px;
  
  img {
    transform: translateY(0) scale(1.2);
  }

  .description { 
    color: #e6e6e6;
  }
}

.image-drink {
  width: 200px;  
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
  margin-top: 20px;
  transition: 0.3s ease;
}

.cart-btn:hover {
  background-color: #ebebeb;
}

.cart-icon {
  font-size: 16px;
  vertical-align: auto;
}

</style>