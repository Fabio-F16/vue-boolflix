<template>
  <div id="app">
    <HeaderComponent @searchEmit="loadData" />
    <MainComponent />
  </div>
</template>

<script>
import HeaderComponent from "./components/HeaderComponent.vue";
import MainComponent from "./components/MainComponent.vue";
import axios from "axios";

export default {
  name: "App",
  data() {
    return {
      apiUrl: "https://api.themoviedb.org/3/search/",
      apiKey: "7b0221641cd6cccd42ea4445b3c56e3d",
      query: "",
    };
  },
  components: {
    HeaderComponent,
    MainComponent,
  },

  methods: {
    // searching(textToSearch) {
    //   // console.log(textToSearch);
    //   this.query = textToSearch;
    //   console.log(this.query);
    // },
    loadData(textToSearch) {
      this.query = textToSearch;
      console.log(this.query);
      const params = {
        query: this.query,
        api_key: this.apiKey,
      };
      axios
        .get(this.apiUrl + "tv", { params })
        .then((response) => {
          console.log(response.data.results);
        })
        .catch((error) => {
          console.log("error" + error);
        });
    },
  },
};
</script>

<style lang="scss">
#app {
}
</style>
