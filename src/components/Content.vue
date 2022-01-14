<template>
  <section class="content">
    <h3 class="brand">{{brand}}</h3>
    <h3 class="name">{{name}}</h3>
    <p class="description">{{description}}</p>
    <div class="price-wrapper">
      <div class="price">{{ formatPrice(price) }}</div>
      <div class="discount">{{discount}}%</div>
      <div class="price-old">{{ formatPrice(priceOld) }}</div>
    </div>

    <div class="buy-selector-container">
      <QuantitySelector 
        v-bind="$props"
        />
      <Button class="btn cta">Add to cart</Button>
    </div>
  </section>
</template>

<script>
import Button from './Button.vue'
import QuantitySelector from './QuantitySelector.vue'

export default {
  name: "Content",
  components: {
    Button,
    QuantitySelector
  },
  props: {
    brand: String,
    name: String,
    description: String,
    price: Number,
    priceOld: Number,
    discount: Number,
    quantity: Number
  },
  methods: {
    formatPrice (price) {
      return price.toLocaleString('pt-br', { style: 'currency', currency: 'BRL'})
    }
  }
}
</script>