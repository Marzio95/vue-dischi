<template>
  <div class="card col-4 col-md-3 col-lg-2 text-white bkg_card text-center">
    <img class="img mt-4" :src="discoData.poster" :alt="discoData.author" />
    <h4>{{ discoData.title }}</h4>
    <h5 class="text-secondary">{{ discoData.author }}</h5>
    <h5 class="text-secondary">{{ discoData.year }}</h5>
  </div>
</template>

<script>
export default {
  name: "CardDischi",
  props: {
    discoData: Object,
  },
};
</script>

<style scoped lang="scss">
.bkg_card {
  background-color: #2e3a46;
}
h4 {
  text-transform: uppercase;
  margin: 1rem 0;
}
</style>
