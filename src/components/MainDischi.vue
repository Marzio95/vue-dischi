<template>
  <div class="container-fluid bkg_cont">
    <div class="timer" v-if="arrayDischi == null">Pagina in caricamento</div>
    <div v-else class="container">
      <div class="row gap-4 justify-content-center p-5">
        <Card-dischi
          v-for="album in changeMusicFunction()"
          :key="album.title"
          :disco-data="album"
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
      arrayDischiFiltered: null,
    };
  },
  props: {
    selectedGenere: String,
  },
  components: {
    CardDischi,
  },
  created() {
    setTimeout(() => {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((response) => {
          this.arrayDischi = response.data.response;
        });
    }, 3000);
  },
  methods: {
    changeMusicFunction() {
      if (this.selectedGenere.toLowerCase() == "general") {
        return this.arrayDischi;
      } else {
        this.arrayDischiFiltered = this.arrayDischi.filter((element) => {
          return (
            element.genre.toLowerCase() == this.selectedGenere.toLowerCase()
          );
        });
      }

      return this.arrayDischiFiltered;
    },
  },
};
</script>

<style scoped lang="scss">
.bkg_cont {
  background-color: #1e2d3b;
}
.timer {
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 4rem;
  height: 90vh;
  color: white;
}
</style>
