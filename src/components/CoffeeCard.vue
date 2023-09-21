<template>
  <div class="coffee-card">
    <div>
      
    </div>
    <div class="details">
      <div class="details-header">
        <span>{{ item.name }}</span>
        <span>${{ item.price }}</span>
      </div>
      <span>{{ item.description }}</span>
      <div class="actions-btn">
        <button type="button">Shop now</button>
        <button type="button">Add cart</button>
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
  created() {
    console.log(this.item)
  }
}

</script>

<style>
.coffee-card {
  width: 355px;
  height: 421px;
  background-color: #FFFFFF;
  border-radius: 10px;
}

</style>