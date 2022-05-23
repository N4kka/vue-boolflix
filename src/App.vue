<template>
  <div id="app">
    <!-- HEADER -->
    <AppHeader @search="[searchMovies($event), tvSeries($event)]" />
    <!-- /HEADER -->

    <!-- MAIN -->
    <AppMain :movies="movies" :tvSeries="tvShows" />

    <!-- /MAIN -->
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    AppHeader,
    AppMain,
  },
  data() {
    return {
      movies: [],
      tvShows: [],
    };
  },
  methods: {
    searchMovies(querySearch) {
      axios
        .get(
          `https://api.themoviedb.org/3/search/movie?api_key=e42f888f287ca2fbe26c9a6e70351fb7&query=${querySearch}`
        )
        .then((resp) => {
          this.movies = resp.data.results;
          console.log(this.movies);
        });
    },
    tvSeries(querySearch) {
      axios
        .get(
          `https://api.themoviedb.org/3/search/tv?api_key=e42f888f287ca2fbe26c9a6e70351fb7&query=${querySearch}`
        )
        .then((response) => {
          this.tvShows = response.data.results;
          console.log(this.tvShows);
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
