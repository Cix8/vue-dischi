<template>
  <header class="d-flex align-items-center justify-content-between">
    <div class="icon-container">
      <i class="fab fa-spotify"></i>
    </div>
    <div class="d-flex px-3">
      <select
        role="button"
        class="form-select text-muted fw-bold me-3"
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
      <div class="input-group">
        <span class="input-group-text" id="basic-addon1"
          ><i class="fas fa-search"></i
        ></span>
        <input
          type="text"
          class="form-control"
          placeholder="Author"
          aria-label="Author"
          aria-describedby="basic-addon1"
          v-model="thisAuthor"
          @keyup="$emit('userChoice', thisAuthor)"
        />
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "AppHeader",
  data() {
    return {
      thisGenre: "",
      thisAuthor: "",
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

  select:focus,
  input:focus {
    border-color: #1ed55e;
    box-shadow: 0 0 0 0.25rem rgb(30 213 94 / 25%);
  }
}
</style>
