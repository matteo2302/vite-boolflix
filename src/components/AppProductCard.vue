<script>
export default {
  props: {
    product: Object
  },
  computed: {
    hasFlag() {
      let avaibleFlag = ['it', 'en'];
      return avaibleFlag.includes(this.product.original_language)
    },
    flagSrc() {
      const url = new URL(`../assets/${this.product.original_language}.png`, import.meta.url);
      return url.href
    },
    halfRate() {
      return Math.ceil(this.product.vote_average / 2)
    },
    poster() {
      const url = new URL(`./w780${this.product.backdrop_path}`, import.meta.url);
      return url.href
    }
  }
}
</script>
<template>
  <ul class="list-group list-group-flush">
    <li class="list-group-item">
      <div><img :src="poster" :alt="product.name"></div>
      <div>{{ product.title || product.name }}</div>
      <div>{{ product.original_title || product.name }}</div>
      <div><img v-if="hasFlag" :src="flagSrc" :alt="product.original_language">
        <span v-else>{{ product.original_language }} </span>
      </div>
      <div>{{ halfRate }}</div>
    </li>
  </ul>
</template>
<style scoped></style>