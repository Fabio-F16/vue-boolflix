<template>
  <div>
    <FilmsList v-for="(film, index) in films" :key="index" :tv="film" />
  </div>
</template>

<script>
import FilmsList from "./FilmsList.vue";
// import VueFlags from "@growthbunker/vueflags";

export default {
  name: "MainComponent",
  components: {
    FilmsList,
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