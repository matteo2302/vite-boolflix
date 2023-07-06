<script>
import ProductSection from './ProductSection.vue'
import { store } from '../data/store.js'
export default {
  data() {
    return {
      store
    }
  },
  components: {
    ProductSection
  }
}
</script>
<template>
  <div class="container">
    <ProductSection title="Movies" id="movies" :products="store.movies" />
    <ProductSection title="Series" id="tv-series" :products="store.series" />

  </div>
</template>
<style scoped></style>