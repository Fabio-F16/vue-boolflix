<template>
  <div>
    <div class="card">
      <img :src="pathImg" alt="tv.original_title" />
      <h2>{{ tv.original_title }}</h2>
      <h5>{{ tv.original_title }}</h5>
      <p>{{ tv.original_language }}</p>

      <p>{{ tv.vote_average }}</p>
      <p>Films list</p>
    </div>
    <!-- https://image.tmdb.org/t/p/w342/wwemzKWzjKYJFfCeiB57q3r4Bcm.png -->
  </div>
</template>

<script>
export default {
  name: "FilmsLst",
  data() {
    return {
      pathUrl: "https://image.tmdb.org/t/p/",
    };
  },
  props: {
    tv: Object,
  },
  computed: {
    pathImg() {
      const percorsoImg = this.pathUrl + "w500" + this.tv.poster_path;
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