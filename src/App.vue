<template>
  <div id="app">
    <header>
      <div class="icon-container">
        <i class="fab fa-spotify"></i>
      </div>
    </header>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
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
</style>
