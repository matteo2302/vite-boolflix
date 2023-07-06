<script>
export default {
  props: {
    product: Object
  },
  // methods: {
  //   getStars(fullStar) {
  //     for (i = 0; i < 5; i++) {
  //       if (i < fullStar) {
  //         <i class="fa-solid fa-star"></i>;
  //       } else {
  //         <i class="fa-regular fa-star"></i>;
  //       } return
  //     }

  //   }
  // },
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

  }
}
</script>
<template>
  <ul class="list-group list-group-flush">
    <li class="list-group-item">
      <div v-if="product.poster_path"><img :src="`https://image.tmdb.org/t/p/w342${this.product.poster_path}`"
          :alt="product.name"></div>
      <div>{{ product.title || product.name }}</div>
      <div>{{ product.original_title || product.name }}</div>
      <div><img v-if="hasFlag" :src="flagSrc" :alt="product.original_language">
        <span v-else>{{ product.original_language }} </span>
      </div>
      <div><i v-for=" i in  5 " class="fa-star" :class="[i < halfRate ? 'fa-solid' : 'fa-regular']"></i>;
      </div>
    </li>
  </ul>
</template>
<style scoped></style>