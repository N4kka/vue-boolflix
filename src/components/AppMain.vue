<template>
  <main>
    <div class="movies-card">
      <h1>MOVIES</h1>
      <ul class="card">
        <li
          v-for="(item, index) in movies"
          :key="index"
          :style="{
            backgroundImage: `url(http://image.tmdb.org/t/p/w342${item.poster_path})`,
            height: '250px',
            backgroundSize: 'cover',
          }"
        >
          <h4>{{ item.title }}</h4>
          <h4>{{ item.original_title }}</h4>
          <FlagIcon :languageCode="item.original_language">{{
            item.original_language
          }}</FlagIcon>
          <h4 v-for="number in newRating(item.vote_average)" :key="number">
            {{ newRating }}
            <i v-for="number in 5" :key="number" class="fas fa-star"></i>
          </h4>
        </li>
      </ul>
    </div>
    <div class="tvseries-card">
      <h1>TV SERIES</h1>
      <ul class="card">
        <li
          v-for="(item, i) in tvSeries"
          :key="'A' + i"
          :style="{
            backgroundImage: `url(http://image.tmdb.org/t/p/w342${item.poster_path})`,
            backgroundSize: 'cover',
            height: '250px',
          }"
        >
          <h4>{{ item.name }}</h4>
          <h4>{{ item.original_name }}</h4>
          <FlagIcon :languageCode="item.original_language">{{
            item.original_language
          }}</FlagIcon>
          <h4 v-for="number in newRating(item.vote_average)" :key="number">
            {{ newRating }}
          </h4>
          <i v-for="number in 5" :key="number" class="fas fa-star"></i>
        </li>
      </ul>
    </div>
  </main>
</template>

<script>
import FlagIcon from "./FlagIcon.vue";

export default {
  name: "AppMain",
  props: {
    movies: Array,
    tvSeries: Array,
  },
  computed: {
    newRating(item) {
      let actualVote = item.vote_average;
      console.log(actualVote);
      let newRate = 0;
      newRate = parseInt(Math.ceil(actualVote / 2));
      console.log(newRate);
      return newRate;
    },
  },
  components: {
    FlagIcon,
  },
};
</script>

<style scoped lang="scss">
@import "~flag-icons/css/flag-icons.css";
@import "~@fortawesome/fontawesome-free/css/all.min.css";

main {
  background-color: pink;

  .movies-card,
  .tvseries-card h1 {
    text-align: center;
  }

  .card {
    display: flex;
    flex-wrap: wrap;
    list-style: none;

    li {
      width: calc(100% / 4);
      color: white;
      font-size: 20px;
      img {
        width: 15%;
      }
    }
  }
}
</style>