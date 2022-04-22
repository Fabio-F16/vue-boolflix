<template>
  <div
    @mouseover="isOver"
    @mouseleave="isLeave"
    class="ff-card col-12 col-md-2"
  >
    <div v-if="!cardOver">
      <img :src="pathImg" alt="tv.id" />
    </div>
    <div v-else class="info">
      <div class="d-flex">
        <b>Titolo: </b>
        <p>{{ tv.original_title }}</p>
      </div>

      <div class="d-flex">
        <b>Titolo originale: </b>
        <p>{{ tv.original_title }}</p>
      </div>

      <div class="d-flex">
        <b>Lingua: </b>
        <p>{{ tv.original_language }}</p>
      </div>

      <div class="d-flex">
        <b>Voto: </b>
        <p>{{ tv.vote_average }}</p>
      </div>

      <div class="d-flex">
        <b>Overview: </b>
        <p>{{ tv.overview }}</p>
      </div>

      <p>Films list</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "FilmsLst",
  data() {
    return {
      pathUrl: "https://image.tmdb.org/t/p/",
      size: "w342",
      cardOver: false,
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
  methods: {
    isOver() {
      this.cardOver = true;
    },
    isLeave() {
      this.cardOver = false;
    },
  },
};
</script>

<style lang="scss" scoped>
.ff-card {
  height: 315px;
  // overflow-y: auto;
  // overflow-y: auto;
  font-size: 0.8rem;
}
img {
  width: 100%;
}
.info {
  padding: 10px;
  color: white;
  background-color: #141414;
  height: 100%;
  overflow-y: scroll;
}
p {
  text-transform: uppercase;
}
</style>