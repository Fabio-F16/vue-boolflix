<template>
  <div>
    <div class="card">
      <h2>{{ tv.title }}</h2>
      <h5>{{ tv.original_title }}</h5>
      <p>{{ tv.original_language }}</p>

      <p>{{ tv.vote_average }}</p>
    </div>
    <!-- <div class="card">
      <h2>{{ serie.name }}</h2>
      <h5>{{ serie.original_name }}</h5>
      <p>{{ serie.original_language }}</p>

      <p>{{ serie.vote_average }}</p>
    </div>
  </div> -->
</template>

<script>
// import VueFlags from "@growthbunker/vueflags";

export default {
  name: "MainComponent",
  props: {
    tv: Object,
    // serie: Object,
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