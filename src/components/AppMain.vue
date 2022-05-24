<template>
  <main>
    <div class="container">
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
            <i
              v-for="number in item.starRating"
              :key="'B' + number"
              class="fas fa-star yellow"
            ></i>
            <i
              v-for="number in 5 - item.starRating"
              :key="number"
              class="far fa-star yellow"
            ></i>
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
            <i
              v-for="number in item.starRating"
              :key="number"
              class="fas fa-star yellow"
            ></i>
            <i
              v-for="number in 5 - item.starRating"
              :key="'C' + number"
              class="far fa-star yellow"
            ></i>
          </li>
        </ul>
      </div>
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
  components: {
    FlagIcon,
  },
};
</script>

<style scoped lang="scss">
@import "~flag-icons/css/flag-icons.css";
@import "~@fortawesome/fontawesome-free/css/all.min.css";

main {
  background-color: #1b1b1b;

  .container {
    width: 90%;
    margin: 0 auto;

    .movies-card,
    .tvseries-card h1 {
      color: white;
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
        .yellow {
          color: yellow;
        }
      }
    }
  }
}
</style>