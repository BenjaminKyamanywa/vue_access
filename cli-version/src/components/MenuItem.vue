<template>
    <div>
      <div class="menu-item">
          <img
            class="menu-item__image"
            :src="image.source"
            :alt="image.alt"
          />
          <div>
            <h3>{{ name }}</h3>
            <p v-if="inStock">In Stock</p>
            <p v-else>Out of Stock</p>
            <div>
              <label for="add-item-quantity"
                >Quantity: {{ quantity }}</label
              ><p></p>
              <input
                id="add-item-quantity"
                v-model.number="quantity" 
                type="number"
              /><p></p>
              <button @click="addToShoppingCart(quantity)">
                Add to Shopping Cart
              </button>
            </div>
          </div>
        </div>
    </div>
</template>

<script>

export default {
  name: 'MenutItem',
  props: ['addToShoppingCart', 'image', 'inStock', 'name', 'quantity']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.menu-item {
  display: flex;
  width: 500px;
  justify-content: space-between;
  margin-bottom: 30px;
}

.menu-item__image {
  max-width: 300px;
}

</style>
