<script>
import { store } from './data/store'
export default {
  data() {
    return {
      store
    }
  }
}
</script>
<template>
  <div class="card" style="width: 18rem;">
    <ul class="list-group list-group-flush">
      <li v-for="movie in store.movies" class="list-group-item" :key="movie.id">
        <div>{{ movie.title }}</div>
        <div>{{ movie.original_title }}</div>
        <div>{{ movie.original_language }} </div>
        <div>{{ movie.vote_average }}</div>
      </li>

    </ul>
  </div>
</template>
<style scoped></style>