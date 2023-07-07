<script>
import AppProductCard from './AppProductCard.vue';
export default {
  components: { AppProductCard, AppProductCard },
  props: {
    id: String,
    title: String,
    products: Array
  }
}
</script>
<template>
  <h2>{{ title }}</h2>
  <section class="d-flex flex-wrap container justify-content-between" :id="id">
    <AppProductCard v-for="product in  products" :key="product.id" :product="product" />
  </section>
</template>
<style scoped>
h2 {
  color: white;
}

.container {
  width: 1400px;
}
</style>