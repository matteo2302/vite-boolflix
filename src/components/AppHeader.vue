<script>
import AppSearch from './AppSearch.vue';
export default {
  components: { AppSearch },
  emits: ['title-searched']
}
</script>
<template>
  <div class="mt-5">
    <h1>BOOLFIX</h1>
    <AppSearch @title-wrote="$emit('title-searched', title)" />
  </div>
</template>
<style scoped>
div {
  display: flex;

  justify-content: space-between;
}

h1 {
  color: red;
}
</style>