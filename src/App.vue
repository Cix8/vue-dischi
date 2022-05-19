<template>
  <div id="app">
    <template v-if="loading">
      <div
        class="loading-icon w-100 vh-100 d-flex flex-column justify-content-center align-items-center"
      >
        <i class="fas fa-running"></i>
        <p class="fw-bold">LOADING...</p>
      </div>
    </template>
    <template v-else>
      <header>
        <div class="icon-container">
          <i class="fab fa-spotify"></i>
        </div>
      </header>
      <main class="py-5">
        <ProductsList :productsArray="mainData" />
      </main>
    </template>
  </div>
</template>

<script>
import ProductsList from "./components/ProductsList.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    ProductsList,
  },
  data() {
    return {
      mainData: [],
      loading: true,
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((resp) => {
        this.mainData = resp.data.response;
        this.loading = false;
      });
  },
};
</script>

<style lang="scss">
@import "./style/common.scss";

#app {
  background-color: #1e2d3b;

  .loading-icon {
    font-size: 60px;
    color: #1ed55e;

    i {
      font-size: 100px;
    }
  }
  header {
    padding: 10px 20px;
    background-color: #2e3a46;
    font-size: 50px;
    color: #1ed55e;
  }
}
</style>
