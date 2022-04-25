<template>
  <div class="main">
    <div class="container d-flex justify-content-center">
      <FilmsList v-for="(film, index) in films" :key="index" :tv="film" />
      <SeriesList v-for="serie in series" :key="serie.id" :serie="serie" />
    </div>
  </div>
</template>

<script>
import FilmsList from "./FilmsList.vue";
import SeriesList from "./SeriesList.vue";
// import VueFlags from "@growthbunker/vueflags";

export default {
  name: "MainComponent",
  components: {
    FilmsList,
    SeriesList,
  },
  props: {
    films: Array,
    series: Array,
  },
};
</script>

<style lang="scss" scoped>
.main {
  background-color: #141414;
  height: calc(100vh - 75px);
  overflow-y: auto;
}
.container {
  flex-wrap: wrap;
}
</style>