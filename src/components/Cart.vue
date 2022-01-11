<template>
  <div class="cart">
    <h1 class="cart-title">Cart</h1>
    <div class="cart-content">
      <div class="cart-product">
        <EImage />
        <div class="cart-product-content">
          <div class="product-name">{{productName}}</div>
          <div class="price">{{formatPrice(price)}}</div>
          <div class="product-quantity">x{{productQuantity}}</div>
          <div class="total-price">{{formatPrice(totalPrice)}}</div>
        </div>
      </div>
      <Button class="btn cta">Checkout</Button>
    </div>
  </div>
</template>

<script>
import EImage from './EImage.vue'
import Button from './Button.vue'

export default {
  name: 'Cart',
  components: {
    EImage,
    Button
  },
  data () {
    return {
      productName: 'Fall Limited Edition Sneakers',
      price: 125,
      productQuantity: 3
    }
  },
  computed: {
    totalPrice () {
      return this.price * this.productQuantity
    }
  },
  methods: {
    formatPrice (price) {
      return price.toLocaleString('pt-br', { style: 'currency', currency: 'BRL'})
    }
  }
}
</script>