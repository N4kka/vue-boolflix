<template>
  <header>
    <h1>BOOLFLIX</h1>
    <div class="searchbar">
      <input
        type="text"
        placeholder="Search Movies"
        v-model="name"
        id="movies"
      />
      <button @click="$emit('search', name)">Search</button>
    </div>
  </header>
</template>

<script>
export default {
  name: "AppHeader",
  data() {
    return {
      name: "",
    };
  },
};
</script>

<style scoped lang="scss">
header {
  height: 100px;
  background-color: black;
  display: flex;
  justify-content: space-between;
  align-items: center;

  h1 {
    color: red;
    line-height: 100px;
    margin-left: 2rem;
  }

  .searchbar {
    margin-right: 2rem;
  }
}
</style>