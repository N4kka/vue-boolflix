<template>
  <header>
    <h1>BOOLFLIX</h1>
    <div class="searchbar">
      <input type="text" name="Searchbar" id="" />
      <button>Search</button>
    </div>
  </header>
</template>

<script>
export default {
  name: "AppHeader",
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