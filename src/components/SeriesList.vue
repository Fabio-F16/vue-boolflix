<template>
  <div
    @mouseover="isOver"
    @mouseleave="isLeave"
    class="ff-card col-12 col-md-2"
  >
    <div v-if="!cardOver">
      <img :src="pathImg" alt="serie.name" />
    </div>
    <div v-else class="info">
      <div class="d-flex">
        <b>Titolo: </b>
        <p>{{ serie.original_name }}</p>
      </div>

      <div class="d-flex">
        <b>Titolo originale: </b>
        <p>{{ serie.original_name }}</p>
      </div>

      <div class="d-flex">
        <b>Lingua: </b>
        <!-- <p>{{ serie.original_language }}</p> -->
        <img
          :src="flagUrl(serie.original_language)"
          :alt="'lang: ' + serie.original_language"
          class="flag"
        />
      </div>

      <div class="d-flex">
        <b>Voto: </b>
        <p>{{ serie.vote_average }}</p>
      </div>

      <div class="d-flex">
        <b>Overview: </b>
        <p>{{ serie.overview }}</p>
      </div>

      <p>series list</p>
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
      cardOver: false,
      logoImg:
        "https://image.tmdb.org/t/p/w342/wwemzKWzjKYJFfCeiB57q3r4Bcm.png",
    };
  },
  methods: {
    isOver() {
      this.cardOver = true;
    },
    isLeave() {
      this.cardOver = false;
    },
    flagUrl(countryCode) {
      switch (countryCode) {
        case "en":
          return `https://raw.githubusercontent.com/emcrisostomo/flags/91286fe015b4957b51bc470eca4b5fd6f5ac90da/svg/US.svg`;
        case "cs":
          return `https://raw.githubusercontent.com/emcrisostomo/flags/91286fe015b4957b51bc470eca4b5fd6f5ac90da/svg/CZ.svg`;
        case "da":
          return `https://raw.githubusercontent.com/emcrisostomo/flags/91286fe015b4957b51bc470eca4b5fd6f5ac90da/svg/DK.svg`;
        case "el":
          return `https://raw.githubusercontent.com/emcrisostomo/flags/91286fe015b4957b51bc470eca4b5fd6f5ac90da/svg/GR.svg`;
        case "ko":
          return `https://raw.githubusercontent.com/emcrisostomo/flags/91286fe015b4957b51bc470eca4b5fd6f5ac90da/svg/KR.svg`;
        case "ja":
          return `https://raw.githubusercontent.com/emcrisostomo/flags/91286fe015b4957b51bc470eca4b5fd6f5ac90da/svg/JP.svg`;
        case "zh":
          return `https://raw.githubusercontent.com/emcrisostomo/flags/91286fe015b4957b51bc470eca4b5fd6f5ac90da/svg/CN.svg`;
        case "hi":
          return `https://raw.githubusercontent.com/emcrisostomo/flags/91286fe015b4957b51bc470eca4b5fd6f5ac90da/svg/IN.svg`;
        case "te":
          return `https://raw.githubusercontent.com/emcrisostomo/flags/91286fe015b4957b51bc470eca4b5fd6f5ac90da/svg/IN.svg`;
        default:
          return `https://raw.githubusercontent.com/emcrisostomo/flags/91286fe015b4957b51bc470eca4b5fd6f5ac90da/svg/${countryCode.toUpperCase()}.svg`;
      }
    },
  },
  computed: {
    pathImg() {
      if (this.serie.poster_path) {
        const percorsoImg = this.pathUrl + "w342" + this.serie.poster_path;
        return percorsoImg;
      } else {
        console.log("noimg");
        return this.logoImg;
      }
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
  margin-top: 30px;
}
img {
  width: 100%;
}
.flag {
  width: 25px;
  margin-left: 10px;
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