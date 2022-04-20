<template>
  <div>
    <div class="card">
      <h2>{{ tv.name }}</h2>
      <h5>{{ tv.original_name }}</h5>
      <p>{{ tv.original_language }}</p>
      <p>{{ tv.vote_average }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "MainComponent",
  props: {
    tv: Object,
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