<template>
  <div class="nav-bar">
    <MenuItem
      v-for="item in menuitemsname"
      :key="item"
    >
      {{item}}
    </MenuItem>
  </div>
</template>

<script>
import MenuItem from './MenuItem.vue'

export default {
  name: "NavBar",
  data () {
    return {
      menuitemsname: ['Collections', 'Men', 'Women', 'About', 'Contact']
    }
  },
  components: {
    MenuItem,
  }
}
</script>

<style>

</style>