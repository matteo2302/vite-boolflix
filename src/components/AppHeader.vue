<script>
import AppSearch from './AppSearch.vue';
export default {
  components: { AppSearch },
  emits: ['title-searched'],
  methods: {
    onInput(title) { this.$emit('title-searched', title); },
  }

};
</script>
<template>
  <div class="container">
    <div class="mt-5 hader-cont">
      <h1>BOOLFIX</h1>
      <AppSearch @title-wrote="onInput" />
    </div>
  </div>
</template>
<style scoped>
div {
  display: flex;
  justify-content: space-between;
}

.hader-cont {
  width: 100%;
}

h1 {
  color: red;
}
</style>