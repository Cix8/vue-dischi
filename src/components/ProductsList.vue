<template>
  <section>
    <div class="container">
      <div class="row row-cols-2 row-cols-md-3 row-cols-lg-5">
        <SingleDisc
          v-for="(item, index) in productsArray"
          :key="index"
          :product="item"
        />
      </div>
    </div>
  </section>
</template>

<script>
import SingleDisc from "./SingleDisc.vue";

export default {
  name: "ProductsList",
  components: {
    SingleDisc,
  },
  props: {
    productsArray: Array,
  },
  data() {
    return {
      products: [],
    };
  },
  created() {
    this.products = this.productsArray;
  },
};
</script>

<style lang="scss" scoped></style>
