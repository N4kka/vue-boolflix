<template>
  <div>
    <span class="fi" :class="`fi-${countryFlag}`"></span>
  </div>
</template>

<script>
export default {
  name: "FlagIcon", 
  props: {
    languageCode: String,
  },
  computed: {
    countryFlag() {
      switch (this.languageCode) {
        case "it":
          return "it";
        case "en":
          return "gb";
        case "es":
          return "es";
        case "de":
          return "de";
        default:
          return "unknown";
      }
    },
  },
};
</script>

<style scoped lang="scss">
.fi-unknown {
  background-image: url(../assets/unknown.png);
}
</style>