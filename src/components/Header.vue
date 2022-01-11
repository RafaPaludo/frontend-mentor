<template>
  <header class="header">
    <div class="logo">
      <img src="../images/logo.svg" alt="Sneakers">
    </div>

    <NavBar />
    <IconCart />
    <Profile />
    <Cart />
  </header>
</template>

<script>
import NavBar from './NavBar.vue'
import IconCart from './IconCart.vue'
import Cart from './Cart.vue'
import Profile from './Profile.vue'

export default {
  name: 'Header',
  components: {
    IconCart,
    Profile,
    NavBar,
    Cart
  }
}
</script>