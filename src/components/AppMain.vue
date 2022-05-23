<template>
  <main>
    <ul v-for="(item, index) in movies" :key="index">
      <li>{{ item.title }}</li>
      <li>{{ item.original_title }}</li>
      <li>{{ item.original_language }}</li>
      <li>{{ item.vote_average }}</li>
    </ul>
  </main>
</template>

<script>
export default {
  name: "AppMain",
  props: {
    movies: Array,
  },
};
</script>

<style scoped lang="scss">
main {
  background-color: pink;
  height: calc(100vh - 100px);

  li {
    color: white;
    font-size: 20px;
  }
}
</style>