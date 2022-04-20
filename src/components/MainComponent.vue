<template>
  <div>
    <FilmsList v-for="(film, index) in films" :key="index" :tv="film" />
    <SeriesList v-for="serie in series" :key="serie.id" :serie="serie" />
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
    // tv: Object,
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