<template>
  <div class="quantity-selector-group">
    <input type="button" value="-" class="button-minus" data-field="quantity"/>
    <input type="number" step="1" max="" value="1" name="quantity" class="quantity-field"/>
    <input type="button" value="+" class="button-plus" data-field="quantity"/>
  </div>
</template>

<script>
export default {
  name: 'QuantitySelector'
}
</script>