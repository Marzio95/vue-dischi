<template>
  <div class="container-fluid">
    <div class="row">
      <div class="b_t text-white flex p-3">
        <h1>SPOTIFY</h1>

        <select
          class="rounded"
          name="generi"
          id="generi"
          v-model="selected"
          @change="$emit('changeMusic', selected)"
        >
          <option default value="general">General</option>
          <option value="rock">Rock</option>
          <option value="jazz">Jazz</option>
          <option value="metal">Metal</option>
          <option value="pop">Pop</option>
        </select>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HeaderDischi",
  data() {
    return {
      selected: "general",
    };
  },
};
</script>

<style scoped lang="scss">
.b_t {
  background-color: #2e3a46;
}
select {
  height: 2.3rem;
  width: 5.5rem;
}
.flex {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
