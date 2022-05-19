<template>
  <div class="col text-center p-3">
    <div class="img-container">
      <img :src="product.poster" :alt="product.author + ', ' + product.title" />
    </div>
    <div class="title text-white">
      <h5 class="fw-bold">{{ product.title }}</h5>
    </div>
    <div class="sub-titles text-muted">
      <h6>{{ product.author }}</h6>
      <span>{{ product.year }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "SingleDisc",
  props: {
    product: Object,
  },
};
</script>

<style lang="scss" scoped>
.col {
  background-color: #2e3a46;
}
</style>
