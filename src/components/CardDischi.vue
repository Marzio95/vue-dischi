<template>
  <div class="card col-lg-2">
    <img class="img" :src="cardSrc" :alt="cardText" />
    <h2>{{ cardText }}</h2>
    <h3>{{ cardAuthor }}</h3>
    <h3>{{ cardYear }}</h3>
  </div>
</template>

<script>
export default {
  name: "CardDischi",
  props: {
    cardSrc: String,
    cardText: String,
    cardAuthor: String,
    cardYear: String,
  },
};
</script>

<style scoped lang="scss"></style>
