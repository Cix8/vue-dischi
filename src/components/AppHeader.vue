<template>
  <header class="d-flex align-items-center justify-content-between">
    <div class="icon-container">
      <i class="fab fa-spotify"></i>
    </div>
    <div>
      <select
        class="form-select text-muted fw-bold"
        aria-label="Default select example"
        v-model="thisGenre"
        @click="$emit('userChoice', thisGenre)"
      >
        <option value="">All Genres</option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
      </select>
    </div>
  </header>
</template>

<script>
export default {
  name: "AppHeader",
  data() {
    return {
      thisGenre: "",
    };
  },
};
</script>

<style lang="scss" scoped>
header {
  padding: 10px 20px;
  background-color: #2e3a46;
  font-size: 50px;
  color: #1ed55e;
}
</style>
