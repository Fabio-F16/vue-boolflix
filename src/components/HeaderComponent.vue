<template>
  <header>
    <div class="container">
      <div class="col-4">
        <img :src="logoImg" alt="logo" />
      </div>
      <div class="col-4 text-end">
        <input
          v-model="textToSearch"
          type="text"
          placeholder="Ricerca serie o film"
          @keyup.enter="sendText"
        />
        <button @click="sendText">Cerca</button>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "HeaderComponent",
  data() {
    return {
      textToSearch: "",
      logoImg:
        "https://image.tmdb.org/t/p/w342/wwemzKWzjKYJFfCeiB57q3r4Bcm.png",
    };
  },
  methods: {
    sendText() {
      this.$emit("searchEmit", this.textToSearch);
    },
  },
};
</script>

<style lang="scss" scoped>
header {
  background-color: black;
}
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 75px;
  img {
    width: 40%;
  }
}
button {
  margin-left: 2%;
}
</style>