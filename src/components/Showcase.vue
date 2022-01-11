<template>
  <div class="showcase">
    <EImage class="main-image" />
    <div class="image-wrapper">
      <EImage v-for="image in images" :key="image" />
    </div>
  </div>
</template>

<script>
import EImage from './EImage.vue'

export default {
  name: "Showcase",
  components: {
    EImage
  },
  data () {
    return {
      images: [0,1,2,3],
    }
  }
}
</script>