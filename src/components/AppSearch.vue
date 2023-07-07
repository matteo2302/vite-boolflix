<script>
export default {
  data: () => ({ title: '' }),
  emits: ['title-wrote'],
}
</script>
<template>
  <div class="input-group mb-3">
    <input @keyup.enter="$emit('title-wrote', title)" v-model.trim="title" type="text" class="form-control"
      placeholder="cerca serie tv o film..." aria-label="Recipient's username" aria-describedby="basic-addon2">
    <span class="input-group-text btn btn-outline-danger" id="basic-addon2">cerca</span>
  </div>
</template>
<style scoped>
span {
  background-color: white;
}

div {
  width: 500px;
}
</style>