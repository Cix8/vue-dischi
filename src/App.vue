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
      <AppHeader @userChoice="selectGenre($event)" />
      <main class="py-5">
        <ProductsList :productsArray="displayData" />
      </main>
    </template>
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import ProductsList from "./components/ProductsList.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    AppHeader,
    ProductsList,
  },
  data() {
    return {
      mainData: [],
      displayData: [],
      selectedGenre: "",
      loading: true,
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((resp) => {
        this.mainData = resp.data.response;
        this.displayData = this.mainData;
        this.loading = false;
      });
  },
  methods: {
    selectGenre(keyWord) {
      this.displayData = this.mainData.filter((element) => {
        if (
          element.genre.includes(keyWord.trim()) ||
          element.author.toLowerCase().includes(keyWord.trim())
        ) {
          return true;
        }
      });
      console.log(this.displayData);
    },
  },
};
</script>

<style lang="scss">
@import "./style/common.scss";

#app {
  .loading-icon {
    font-size: 60px;
    color: #1ed55e;

    i {
      font-size: 100px;
    }
  }
}
</style>
