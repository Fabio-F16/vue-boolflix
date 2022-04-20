<template>
  <header>
    <input
      v-model="textToSearch"
      type="text"
      placeholder="Ricerca serie o film"
      @keyup.enter="sendText"
    />
    <button @click="sendText">Cerca</button>
  </header>
</template>

<script>
export default {
  name: "HeaderComponent",
  data() {
    return {
      textToSearch: "",
    };
  },
  methods: {
    sendText() {
      this.$emit("searchEmit", this.textToSearch);
    },
  },
};
</script>

<style>
</style>