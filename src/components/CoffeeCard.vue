<template>
  <div class="coffee-card">
    <div>
      <img :src="item.image" alt="" class="image-coffee"/>      
    </div>
    <div class="details">
      <div class="details-header">
        <span>{{ item.name }}</span>
        <span>${{ item.price }}</span>
      </div>
      <span class="description">{{ item.description }}</span>
      <div class="actions-btn">
        <div class="type-card" :class="item.type">{{ item.type }}</div>
        <button type="button" class="card-btn">
          <span class="material-symbols-outlined cart-icon">add_shopping_cart</span>
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

.coffee-card {
  width: 355px;
  height: 421px;
  background-color: #FFFFFF;
  border-radius: 10px;
  margin-bottom: 10px;
  text-align: center;
}

.image-coffee {
  width: 200px;
  cursor: pointer;
  transition: transform .3s ease;
}

.image-coffee:hover {
  transform: translateY(0) scale(1.2);
}

.details {
  padding: 0 15px 0 15px;
}

.details-header {
  display: flex;
  justify-content: space-between;
  font-weight: 700;
  margin-bottom: 15px;
}

.description {
  display: block;
  text-align: left;
  justify-items: start;
  color: $gray-800;
  font-weight: 600;
}

.actions-btn {
  display: flex;
  justify-content: space-between;
  margin-top: 20px;
  bottom: 0;
  position: relative;
}

.card-btn {
  background-color: $secondary-color;
  height: 48px;
  width: 48px;
  border: none;
  border-radius: 100%;
  color: white;
  font-size: 16px;
}

.card-btn:hover {
  opacity: 0.9;
  font-weight: 700;
}

.cart-icon {
  font-size: 24px;
  vertical-align: middle;
}

.type-card {
  border-radius: 5px;
  width: 78px;
  height: 31px;
  font-weight: 700;
  text-transform: capitalize;
  cursor: pointer;
}

.ice {
  border: 2px $ice-type solid;
  color: $ice-type;
}

.hot {
  border: 2px $hot-type solid;
  color: $hot-type;
}

</style>