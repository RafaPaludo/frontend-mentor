<template>
  <button @click="doSomething">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "Button",
  methods: {
    doSomething() {
      console.log("Fechou")
    }
  }
}
</script>

<style>

</style>