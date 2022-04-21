<template>
  <div>
    <div class="card">
      <img :src="pathImg" alt="serie.original_title" />
      <h2>{{ serie.name }}</h2>
      <h5>{{ serie.original_name }}</h5>
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
  data() {
    return {
      pathUrl: "https://image.tmdb.org/t/p/",
    };
  },
  computed: {
    pathImg() {
      const percorsoImg = this.pathUrl + "w342" + this.serie.poster_path;
      return percorsoImg;
    },
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