<template>
  <div>
    <div class="card">
      <h2>{{ serie.title }}</h2>
      <h5>{{ serie.original_title }}</h5>
      <p>{{ serie.original_language }}</p>

      <p>{{ serie.vote_average }}</p>
      <p>Series list</p>
    </div>
  </div>
</template>

<script>
// import VueFlags from "@growthbunker/vueflags";

export default {
  name: "SeriesList",
  props: {
    serie: Object,
  },
};
</script>

<style lang="scss" scoped>
h2 {
  color: red;
}
p {
  text-transform: uppercase;
}
</style>