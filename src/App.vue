<template>
  <div id="app">
    <!-- HEADER -->
    <AppHeader />
    <!-- /HEADER -->

    <!-- MAIN -->
    <AppMain />
    <!-- /MAIN -->
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

export default {
  name: "App",
  components: {
    AppHeader,
    AppMain,
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
