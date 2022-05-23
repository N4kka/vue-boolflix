<template>
  <main>
    <ul v-for="(item, index) in movies" :key="index">
      <li>
        <h4>{{ item.title }}</h4>
        <h4>{{ item.original_title }}</h4>
        <FlagIcon :languageCode="item.original_language">{{
          item.original_language
        }}</FlagIcon>
        <h4>
          {{ item.vote_average }}
        </h4>
      </li>
    </ul>
    <ul v-for="(element, i) in tvSeries" :key="'A' + i">
      <li>
        <h4>{{ element.name }}</h4>
        <h4>{{ element.original_name }}</h4>
        <FlagIcon :languageCode="element.original_language">{{
          element.original_language
        }}</FlagIcon>
        <h4>{{ element.vote_average }}</h4>
      </li>
    </ul>
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

main {
  background-color: pink;
  height: calc(100vh - 100px);

  li {
    color: white;
    font-size: 20px;
  }
}
</style>