<template>
  <div id="app">
    <Header />

    .

    <main class="main">
      <Showcase />
      <Content 
        :brand="product.brand"
        :name="product.name"
        :description="product.description"
        :price="product.price"
        :priceOld="product.oldPrice"
        :discount="discount"
        :quantity="product.quantity"
        />
        {{product.title}}
    </main>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Showcase from './components/Showcase.vue'
import Content from './components/Content.vue'

export default {
  name: 'App',
  components: {
    Header,
    Content,
    Showcase
  },
  data () {
    return {
      product: {
        name: 'Fall Limited Edition Sneakers',
        description: 'These low-profile sneakers are yout perfect casual wear companion. Featuring a durable rubbber outer sole, they will withstand everything the waether can offer',
        brand: 'sneaker company',
        price: 125,
        oldPrice: 250,
        quantity: 5,
        images: {
          image1: '../images/image-product-1.jpg',
          imageThumbnail1: '../images/image-product-1-thumbnail.jpg',
          image2: '../images/image-product-2.jpg',
          imageThumbnail2: '../images/image-product-2-thumbnail.jpg',
          image3: '../images/image-product-3.jpg',
          imageThumbnail3: '../images/image-product-3-thumbnail.jpg',
          image4: '../images/image-product-4.jpg',
          imageThumbnail4: '../images/image-product-4-thumbnail.jpg'
        }
      }
    }
  },
  computed: {
    discount () {
      return this.product.price * 100 / this.product.oldPrice
    }
  }
}
</script>

<style>
/* Todo estilo aqui */
@import url('https://fonts.googleapis.com/css2?family=Kumbh+Sans:wght@400;700&display=swap');

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Kumbh Sans', sans-serif;
}

:root {
  --primary: var(hsl(26, 100%, 55%));
  --pale-orange: var(hsl(25, 100%, 94%));

  --dark-blue: var(hsl(220, 13%, 13%));
  --dark-gray-blue: var(hsl(219, 9%, 45%));
  --grayish-blue: var(hsl(220, 14%, 75%));
  --light-grayish-blue: var(hsl(223, 64%, 98%));
  --white: var(hsl(0, 0%, 100%));
  --black: var(hsl(0, 0%, 0%));
}

#app {
  max-width: 1130px;
  margin: 0 auto;
}

/* Header */
.header {
  padding: 24px 10px;
  display: flex;
  flex-wrap: nowrap;
  justify-content: flex-start;
  align-items: center;
  border-bottom: 1px solid hsl(223, 64%, 98%);
  position: relative;
}


/* Logo */
.logo {
  margin-right: 50px;
}

/* NavBar */
.nav-bar {
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  gap: 24px;
  flex: 1;
}

.menu-item {
  font-size: 20px;
  color: #000;
  text-decoration: none;
  font-weight: 700;
  position: relative;
  padding: 10px 0;
}

.menu-item::after {
  content: '';
  width: 100%;
  height: 4px;
  background: orange;
  position: absolute;
  top: 67px;
  left: 0;
  cursor: none;
  pointer-events: none;
  opacity: 0;
}

.menu-item:hover::after{
  opacity: 1;
}

/* Cart */
.icon-cart {
  margin-right: 50px;
  cursor: pointer;
}

.cart {
  display: block;
  width: 360px;
  height: 265px;
  position: absolute;
  top: 85px;
  right: 0;
  border-radius: 4px;
  box-shadow: 0px 3px 4px rgba(0, 0, 0, 0.14), 0px 3px 3px rgba(0, 0, 0, 0.12), 0px 1px 8px rgba(0, 0, 0, 0.2);
  background: #fff;
}

.cart-title {
  padding: 16px;
  font-size: 24px;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-color: hsl(223, 64%, 98%);
}

.cart .image {
  width: 60px;
}

.cart-content {
  padding: 16px;
}

.cart-content .btn {
  margin: 12px 0;
}

.cart-product {
  display: flex;
  flex-wrap: nowrap;
  justify-content: flex-start;
  align-items: center;
  gap: 10px;
  margin-bottom: 12px;
}

.cart-product-content {
  display: flex;
  flex-wrap: wrap;
  column-gap: 5px;
}

.cart-product-content .product-name {
  width: 100%;
}

.cart-product-content .price {
  font-size: 16px;
  font-weight: 400;
  color: hsl(220, 14%, 75%);
}

/* Profile */
.profile {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  cursor: pointer;
  border: 2px solid transparent;
}

.profile:hover {
  border-color: hsl(26, 100%, 55%);
}

.profile img{
  width: 100%;
}

.main {
  margin: 90px 0;
  display: flex;
  flex-wrap: wrap;
}

/* Showcase */
.showcase {
  flex-basis: 50%;
  padding: 0 50px;
}

.image img {
  border-radius: 12px;
  width: 100%;
}

.image-wrapper {
  display: flex;
  gap: 25px;
  margin: 10px 0;
}

.image-wrapper .image img {
  border: 2px solid transparent;
  cursor: pointer;
}

.image-wrapper .image img:hover {
  border: 2px solid hsl(26, 100%, 55%);
  opacity: .5;
}

/* Content */
.content {
  flex-basis: 50%;
  padding: 0 50px;
}

.brand {
  text-transform: uppercase;
  color: hsl(26, 100%, 55%);
  font-size: 16px;
}

.name {
  font-size: 42px;
  font-weight: 700;
  margin: 25px 0 30px;
}

.description {
  margin: 10px 0;
  color: hsl(219, 9%, 45%);
  line-height: 1.5;
}

.price-wrapper {
  margin: 10px 0;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
}

.price {
  font-size: 32px;
  font-weight: 700;
}

.price-old {
  width: 100%;
  margin-top: 8px;
  color: hsl(220, 14%, 75%);
  text-decoration: line-through;
  font-weight: 700;
}

.discount {
  color: hsl(26, 100%, 55%);
  background: hsl(25, 100%, 94%);
  font-weight: 700;
  margin-left: 12px;
  padding: 4px 8px;
  border-radius: 6px;
}

.buy-selector-container {
  display: flex;
  flex-wrap: nowrap;
  justify-content: center;
  align-items: center;
  gap: 16px;
}

.cta {
  background: hsl(26, 100%, 55%);
  color: #fff;
  font-weight: 700;
  font-size: 16px;
  border-radius: 8px;
  padding: 8px;
  width: 100%;
  height: 44px;
}

.cta:hover {
  opacity: .5;
}

.quantity-selector-group {
  display: flex;
  flex-wrap: nowrap;
  justify-content: center;
  align-items: center;
  background: hsl(223, 64%, 98%);
  border-radius: 8px;
  padding: 5px;
  max-width: 30%;
}

.button-minus,
.button-plus {
  color: hsl(26, 100%, 55%);
  background: hsl(223, 64%, 98%);
  font-size: 24px;
  font-weight: 700;
  border: none;
  width: 50px;
  padding-bottom: 4px;
  cursor: pointer;
}

.quantity-field {
  font-size: 16px;
  background: hsl(223, 64%, 98%);
  border: none;
  text-align: center;
  width: 55px;
}

input::-webkit-inner-spin-button {
  display: none;
}

button {
  width: fit-content;
  background: #fff;
  border: none;
  font-size: 20px;
  font-weight: 700;
  cursor: pointer;
}

</style>
