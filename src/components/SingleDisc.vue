<template>
  <div class="col text-center py-4">
    <div class="img-container d-inline-block mx-auto">
      <img :src="product.poster" :alt="product.author + ', ' + product.title" />
    </div>
    <div class="title text-white mx-auto py-3">
      <h5 class="fw-bold text-uppercase">{{ product.title }}</h5>
    </div>
    <div class="sub-titles text-muted mx-auto">
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
  border: 10px solid #1e2d3b;

  .img-container {
    width: 150px;
    height: 150px;
  }

  .title,
  .sub-titles {
    max-width: 150px;
  }
}
</style>
