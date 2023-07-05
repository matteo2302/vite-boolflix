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
      <li v-for="serie in store.series" class="list-group-item" :key="serie.id">
        <div>{{ serie.name }}</div>
        <div>{{ serie.original_name }}</div>
        <div>{{ serie.original_language }} </div>
        <div>{{ serie.vote_average }}</div>
      </li>

    </ul>
  </div>
</template>
<style scoped></style>