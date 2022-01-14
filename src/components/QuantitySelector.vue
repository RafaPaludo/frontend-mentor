<template>
  <div class="quantity-selector-group">
    <input 
      type="button"
      value="-"
      class="button-minus"
      data-field="quantity"
      @click="minus"
      />

    <input 
      type="number" 
      step="1" 
      min="0"
      :max="maxQuantity"
      :value="inputQuantity"
      name="quantity"
      class="quantity-field"
      />

    <input
      type="button"
      value="+"
      class="button-plus"
      data-field="quantity"
      @click="plus"
      />
  </div>
</template>

<script>
export default {
  name: 'QuantitySelector',
  props: {
    quantity: Number
  },
  data () {
    return {
      inputQuantity: 0,
      maxQuantity: this.quantity
    }
  },
  methods: {
    minus(){
      if (this.inputQuantity > 0) {
        this.inputQuantity--
      }
    },
    plus () {
      if (this.inputQuantity < this.maxQuantity) {
        this.inputQuantity++
      }
    }
  }
}
</script>