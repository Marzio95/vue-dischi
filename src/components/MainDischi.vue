<template>
  <div class="container-fluid bkg_cont">
    <div class="container">
      <div class="row gap-4 justify-content-center p-5">
        <Card-dischi
          v-for="disc in arrayDischi"
          :key="disc.text"
          :card-src="disc.poster"
          :card-text="disc.title"
          :card-author="disc.author"
          :card-year="disc.year"
        ></Card-dischi>
      </div>
    </div>
  </div>
</template>

<script>
import CardDischi from "./CardDischi.vue";
import axios from "axios";
export default {
  name: "MainDischi",
  data() {
    return {
      arrayDischi: null,
    };
  },
  components: {
    CardDischi,
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        console.log(response);
        this.arrayDischi = response.data.response;
      });
  },
};
</script>

<style scoped lang="scss">
.bkg_cont {
  background-color: #1e2d3b;
}
</style>
