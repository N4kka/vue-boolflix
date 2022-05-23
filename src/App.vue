<template>
  <div id="app">
    <!-- HEADER -->
    <AppHeader @search="search($event)" />
    <!-- /HEADER -->

    <!-- MAIN -->
    <AppMain :movies="movies" />

    <!-- /MAIN -->
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import axios from "axios";
import { hasFlag } from 'country-flag-icons'

export default {
  name: "App",
  components: {
    AppHeader,
    AppMain,
  },
  data() {
    return {
      movies: [],
    };
  },
  methods: {
    search(querySearch) {
      axios
        .get(
          `https://api.themoviedb.org/3/search/movie?api_key=e42f888f287ca2fbe26c9a6e70351fb7&query=${querySearch}`
        )
        .then((resp) => {
          this.movies = resp.data.results;
        });
    },
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
