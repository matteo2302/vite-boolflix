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
  <section :id="id">
    <h2>{{ title }}</h2>
    <AppProductCard v-for="product in  products" :key="product.id" :product="product" />
  </section>
</template>
<style scoped></style>