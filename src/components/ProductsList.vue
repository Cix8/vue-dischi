<template>
  <div class="container">
    <div class="row row-cols-5">
      <SingleDisc
        v-for="(item, index) in products"
        :key="index"
        :product="item"
      />
    </div>
  </div>
</template>

<script>
import SingleDisc from "./SingleDisc.vue";
import axios from "axios";

export default {
  name: "ProductsList",
  components: {
    SingleDisc,
  },
  data() {
    return {
      products: [],
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((resp) => {
        this.products = resp.data.response;
      });
  },
};
</script>

<style lang="scss" scoped></style>
