<template>
  <div id="app">
    <header>
      <div class="icon-container">
        <i class="fab fa-spotify"></i>
      </div>
    </header>
    <main class="py-5">
      <ProductsList />
    </main>
  </div>
</template>

<script>
import ProductsList from "./components/ProductsList.vue";

export default {
  name: "App",
  components: {
    ProductsList,
  },
};
</script>

<style lang="scss">
@import "./style/common.scss";

header {
  padding: 10px 20px;
  background-color: #2e3a46;

  .icon-container {
    font-size: 50px;
    color: #1ed55e;
  }
}

main {
  background-color: #1e2d3b;
}
</style>
