<template>
  <div class="col-12 col-md-2">
    <!-- <img :src="pathImg" alt="tv.original_title" /> -->

    <img :src="pathImg" alt="tv.id" />
    <h2>{{ tv.original_title }}</h2>
    <h5>{{ tv.original_title }}</h5>
    <p>{{ tv.original_language }}</p>

    <p>{{ tv.vote_average }}</p>
    <p>Films list</p>
  </div>
</template>

<script>
export default {
  name: "FilmsLst",
  data() {
    return {
      pathUrl: "https://image.tmdb.org/t/p/",
      size: "w342",
    };
  },
  props: {
    tv: Object,
  },
  computed: {
    pathImg() {
      const percorsoImg = this.pathUrl + this.size + this.tv.poster_path;
      return percorsoImg;
    },
  },
};
</script>

<style lang="scss" scoped>
.info {
  // display: none;
}
h2 {
  color: red;
}
p {
  text-transform: uppercase;
}
</style>