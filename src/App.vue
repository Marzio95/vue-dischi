<template>
  <div id="app">
    <HeaderDischi />
    <MainDischi />
  </div>
</template>

<script>
import HeaderDischi from "./components/HeaderDischi.vue";
import MainDischi from "./components/MainDischi.vue";

export default {
  name: "App",
  components: {
    HeaderDischi,
    MainDischi,
  },
};
</script>

<style lang="scss">
html {
  font-family: Roboto sans-serif;
}
@import "../node_modules/bootstrap/scss/bootstrap";
</style>
