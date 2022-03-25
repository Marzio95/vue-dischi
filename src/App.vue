<template>
  <div id="app">
    <HeaderDischi @changeMusic="genereChanged" />
    <MainDischi :selected-genere="selected" />
  </div>
</template>

<script>
import HeaderDischi from "./components/HeaderDischi.vue";
import MainDischi from "./components/MainDischi.vue";

export default {
  name: "App",
  data() {
    return {
      selected: "",
    };
  },
  components: {
    HeaderDischi,
    MainDischi,
  },
  methods: {
    genereChanged(selected) {
      this.selected = selected;
    },
  },
};
</script>

<style lang="scss">
html {
  font-family: Roboto sans-serif;
}
@import "../node_modules/bootstrap/scss/bootstrap";
</style>
