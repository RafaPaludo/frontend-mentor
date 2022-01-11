<template>
  <div 
    class="image"
    >
    <img 
      src='../images/image-product-1.jpg'
    />
  </div>
</template>

<script>
export default {
  name: "EImage",
  props: {
    imageSrc: String,
    imageAlt: String,
  }
}
</script>