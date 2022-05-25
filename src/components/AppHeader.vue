<template>
  <header>
    <img src="../assets/boolflix-logo.png" alt=""/>
    <div class="searchbar">
      <input
        type="text"
        placeholder="Search Movies"
        v-model="name"
        id="movies"
      />
      <button class="search-btn" @click="$emit('search', name)">Search</button>
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

  img {
    margin: 25px;
  }

  .searchbar {
    margin-right: 2rem;

    input {
      width: 200px;
      padding: 5px 10px;
      border: 0px solid transparent;
      border-radius: 5px;
      margin-left: 1rem;
      color: red;
      background-color: white;
    }

    .search-btn {
      padding: 5px 20px;
      border: 0px solid light transparent;
      border-radius: 5px;
      margin-left: 1rem;
      color: white;
      background-color: red;
    }
  }
}
</style>